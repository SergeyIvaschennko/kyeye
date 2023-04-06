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
      <form action="">
<!--        <input type="text" placeholder="Почта" name="username" required>-->
<!--        <input type="password" placeholder="Пароль" name="password" required>-->
        <my-input placeholder="Почта" class = "logpas"></my-input>
        <my-input placeholder="Пароль" class = "logpas"></my-input>
        <p><a id = "a1" href="#">Забыли пароль?</a></p>
        <div class="clearfix">
            <my-button class="submit">Войти</my-button>
        </div>
      </form>
      <div class="line"></div>
      <p id = "l">У вас нет аккаунта? <a id = "a2" href="Home.html">Зарегистрироваться</a></p>
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
  /*body {*/
  /*  font-family: Arial, sans-serif;*/
  /*  background-color: #ffffff;*/
  /*  display: flex;*/
  /*  justify-content: center;*/
  /*  align-items: center;*/
  /*  margin: 0;*/
  /*}*/
  .container {
    margin-top: 50px;
    padding: 10px;
    border-radius: 10px;
    max-width: 500px;
  }
  h1 {
    text-align: left;
    margin-top: 25px;
    margin-bottom: 20px;
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
    margin-top: 0;
    margin-bottom: 20px;
  }
  /*input[type="password"] {*/
  /*  width: 100%;*/
  /*  height: 62px;*/
  /*  padding: 10px;*/
  /*  border: 2px solid #0075ff;*/
  /*  border-radius: 5px;*/
  /*  font-size: 21px;*/
  /*  font-family: "Helvetica Neue", sans-serif;*/
  /*  font-weight: normal;*/
  /*}*/
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
  @media screen and (max-width: 500px) {
    input[type="text"],
    input[type="password"],
    button[type="submit"] {
      width: 100%;
      margin-top: 0;
    }
    .container {
      width: 90%;
    }
  }

  p {
    font-family: "Montserrat", sans-serif;
    font-size: 16px;
    margin-bottom: 15px;
    text-align: right;
    color: #575757;
  }
  a {
    text-decoration: none;
  }
  #a1 {
    color: #575757;

  }
  #a2 {
    color: #0075ff;
  }
  #l {
    font-family: "Montserrat", sans-serif;
    font-size: 15px;
    margin-top: 25px;
    text-align: center;
  }
</style>