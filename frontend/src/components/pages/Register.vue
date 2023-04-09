<template>
<!--  <div class="wrapper">-->
<!--    <div class="registration">-->
<!--      <div class="title">Регистрация</div>-->
<!--      <my-input placeholder="E-mail"-->
<!--      v-model="user.email"-->
<!--      required></my-input>-->
<!--      <my-input placeholder="Имя пользователя"-->
<!--      v-model="user.username"-->
<!--      required></my-input>-->
<!--      <my-input placeholder="Имя"-->
<!--      v-model="user.first_name"-->
<!--      required></my-input>-->
<!--      <my-input placeholder="Фамилия"-->
<!--      v-model="user.last_name"-->
<!--      required></my-input>-->
<!--      <my-input placeholder="Пароль"-->
<!--      v-model="user.password"-->
<!--      type="password"-->
<!--      required></my-input>-->
<!--      <my-input placeholder="Пароль (повторить)"-->
<!--      v-model="user.repeat_password"-->
<!--      type="password"-->
<!--      required></my-input>-->
<!--      <div class="button__container">-->
<!--        <my-button class="sign-up"-->
<!--        @click="validateData"-->
<!--        >Зарегистрироваться</my-button>-->
<!--      </div>-->
<!--    </div>-->
<!--    <error-list :errors="errors" class="error-list"></error-list>-->
<!--  </div>-->

  <div class="container">
    <h1>Начнем 😎</h1>
    <form action="">
      <my-input class="text" placeholder="Почта" v-model="user.email" required></my-input>
      <my-input class="text" placeholder="Имя" v-model="user.first_name" required></my-input>
      <my-input class="text" placeholder="Фамилия" v-model="user.last_name" required></my-input>
      <my-input class="text" placeholder="Никнейм" v-model="user.username" required></my-input>
      <my-input class="text" placeholder="Пароль" v-model="user.password" required></my-input>
      <my-input class="text" placeholder="Повторите пароль" v-model="user.repeat_password" required></my-input>
      <my-button class="submit" @click="validateData">Войти</my-button>
    </form>
    <error-list :errors="errors" class="error-list"></error-list>
  </div>
</template>

<script>
import MyInput from "@/components/UI/MyInput.vue";
import ErrorList from "@/components/UX/ErrorList.vue";
import MyButton from "@/components/UI/MyButton.vue";
import {validateEmail, validateName, validatePassword} from "@/components/validators/validators";
import axios from "axios";
import router from "@/components/routers/router";
import {Auth} from "@/components/js/AuthModule";
import {urlBackend} from "@/components/config";


export default {
  name: "Register",
  components: {ErrorList, MyInput, MyButton},
  props: {
    user: {
      type: Object,
      required: true,
      Auth: Auth,
    }
  },
  data(){
    return{
      user: {
        email: "",
        first_name: "",
        last_name: "",
        username: "",
        password: "",
        repeat_password: "",
      },
      errors: []
    }
  },
  methods: {
    async validateData() {
      this.errors = [];
      [
        validatePassword(
            this.user.password,
            this.user.repeat_password,
        ),
        validateEmail(
            this.user.email,
        ),
        validateName(
            'имя',
            this.user.first_name,
        ),
        validateName(
            'фамилию',
            this.user.last_name,
        ),
      ].forEach(errors => {
        this.errors.push(...errors);
      })
      if (this.errors.length === 0) {
        await this.postRequestToBackend().then(async response => {
          if (response) {
            console.log(response.data)
            // Пользователь зарегестрирован
            await Auth.logIn(this.user.email, this.user.password, undefined, true)
            router.push('/account').then()
          }
        }).catch(error => {
          console.log(error)
        })
      }
    },
    async postRequestToBackend() {
      let value = null;
      try {
        await axios({
          method: 'post',
          url: `${urlBackend}/api/user/register/`,
          data: {
            "username": this.user.username,
            "first_name": this.user.first_name,
            "last_name": this.user.last_name,
            "email": this.user.email,
            "password": this.user.password,
          }
        }).then(response => {
          value = response;
        })
      } catch (error) {
        for (const key in error.response.data) {
          this.errors.push(...error.response.data[key])
        }
      }
      return value;
    }
  }
}
</script>

<style scoped>
  * {
    box-sizing: border-box;
  }
  .container {
    margin-top: 50px;
    padding: 10px;
    border-radius: 10px;
    width: 500px;
  }
  h1 {
    text-align: left;
    margin-top: 25px;
    color: #333333;
    font-family: Montserrat, sans-serif;
    font-weight: bold;
    font-size: 40px;
  }
  .text {
    height: 62px;
    padding: 10px;
    border: 2px solid #0075ff;
    border-radius: 5px;
    font-size: 21px;
    font-family: "Helvetica Neue", sans-serif;
    font-weight: normal;
    margin-top: 20px;
  }
  .submit {
    background-color: #0d74f6;
    color: #ffffff;
    border: 3px solid #0075FF;
    border-radius: 5px;
    margin-top: 20px;
  }


</style>