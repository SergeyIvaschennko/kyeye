<template>
<!--  <div class="wrapper">-->
<!--    <div class="authentication" v-if="!Auth.onLogin">-->
<!--      <div class="title">Авторизация</div>-->
<!--      <form @submit.prevent>-->
<!--        <my-input placeholder="E-mail"-->
<!--                  v-model="this.email"-->
<!--                  required-->
<!--        ></my-input>-->
<!--        <my-input placeholder="Пароль"-->
<!--                  v-model="this.password"-->
<!--                  required-->
<!--                  type="password"-->
<!--                  ></my-input>-->
<!--        <div class="forgot__password">-->
<!--          <a>Забыли пароль?</a>-->
<!--        </div>-->
<!--        <my-button @click="logIn">Войти</my-button>-->
<!--      </form>-->
<!--      <div class="text">-->
<!--        У вас нет аккаунта? <a class="link" @click="$router.push('/register')">Зарегистрироваться</a>-->
<!--      </div>-->
<!--    </div>-->
<!--    <my-button v-else @click="Auth.logOut()">Выйти</my-button>-->
<!--    <error-list :errors="errors" class="error-list"></error-list>-->
<!--  </div>-->


    <div class="container">
      <h1>Добро пожаловать 👋</h1>
      <form @submit.prevent>
        <my-input placeholder="Почта"
                  class = "logpas"
                  v-model="this.email"
                  required
        ></my-input>
        <my-input placeholder="Пароль"
                  class = "logpas"
                  v-model="this.password"
                  type="password"
                  required
        ></my-input>
        <p>Забыли пароль?</p>
        <div class="clearfix">
            <my-button class="submit" @click="logIn">Войти</my-button>
        </div>
      </form>
      <div class="line"></div>
      <p id = "a1">У вас нет аккаунта? <a href="Home.html" @click="$router.push('/register')">Зарегистрироваться</a></p>
    </div>

</template>

<script>

import MyInput from "@/components/UI/MyInput.vue";
import MyButton from "@/components/UI/MyButton.vue";
import {Auth} from "@/components/js/AuthModule";
import ErrorList from "@/components/UX/ErrorList.vue";
import {validateEmail, validateName} from "@/components/validators/validators";
import router from "@/components/routers/router";

export default {
  name: "login-form",
  components: {ErrorList, MyButton, MyInput},
  data() {
    return {
      email: "",
      password: "",
      Auth: Auth,
      errors: []
    }
  },
  methods: {

    validateData() {
      [
        validateEmail(
            this.email,
        ),
        validateName(
            'e-mail',
            this.email,
        ),
        validateName(
            'пароль',
            this.password,
        ),
      ].forEach(errors => {
        this.errors.push(...errors);
      })
    },
    async logIn() {
      this.errors = [];
      this.validateData();
      if (this.errors.length === 0) {
        await this.Auth.logIn(this.email, this.password, this.errors)
      }
      if (this.Auth.onLogin) {
        router.push('/account').then()
      }
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
  .logpas {
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
  }

  .line {
    margin-top: 30px;
    width: 100%;
    border-bottom: 1px solid #c1c1c1;
    opacity: 0.7;
  }

  .clearfix::after {
    content: "";
    clear: both;
    display: table;
  }

  p {
    font-family: "Montserrat", sans-serif;
    font-size: 16px;
    margin-bottom: 15px;
    text-align: right;
    color: #575757;
    margin-top: 15px;
  }

  a {
    text-decoration: none;
    color: #0075ff;
  }
  #a1 {
    text-align: center;
    margin-top: 30px;
  }
</style>