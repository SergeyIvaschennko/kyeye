<template>
  <my-header></my-header>
  <div class="line"></div>
  <div class = "content">
    <h1>ОЧЕРЕДЬ:</h1>
    <h1>БАЗА ДАННЫХ</h1>

    <box-user-in-line>
      <template v-slot:type>Сейчас первый в очереди</template>
      <template v-slot:user>Tage Tompson</template>
    </box-user-in-line>
    <box-user-in-line>
      <template v-slot:type>Следующий</template>
      <template v-slot:user>Tage Tompson</template>
    </box-user-in-line>

    <form action="###">
      <my-button class="black">Посмотреть всю очередь</my-button>
    </form>
  </div>
</template>

<script>
import BoxUserInLine from "@/components/UI/BoxUserInLine.vue";
import MyButton from "@/components/UI/MyButton.vue";
import MyHeader from "@/components/UI/Header.vue";

export default {
  name: "CurrentLine",
  components: {MyHeader, MyButton, BoxUserInLine}
}
</script>

<style scoped>
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.content {
  padding: 15px;
  height: auto;
}

.line {
  width: 100%;
  border-bottom: 1px solid #707070;
}

h1 {
  font-family: "Montserrat", sans-serif;
  font-weight: 900;
  font-size: 36px;
  align-self: flex-start;
  color: #333333;
  margin-top: 0;
  margin-bottom: 0;
}

h2 {
  font-family: 'Montserrat', sans-serif;
  font-weight: bold;
  font-size: 20px;
  color: #ffffff;
  margin-left: 16px;
  margin-top: 0;
  margin-bottom: 12px;
}
h3 {
  font-family: "Montserrat", sans-serif;
  font-weight: 900;
  font-size: 23px;
  color: #0075FF;
}
form {
  width: 100%;
}
body {
  margin: 0;
}
.black {
  background-color: #333333;
  border: 3px solid #333333;
}

</style>