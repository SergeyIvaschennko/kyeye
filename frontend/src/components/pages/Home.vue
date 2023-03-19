<template>
  <div class = "header">
    <a class="logo" href = "###">КУЕУЕ</a>
    <a class="circle" href = "###"></a>
  </div>
  <div class = "content">

    <my-button class="make">Создать очередь</my-button>
<!--    <div id="modal-background"></div>-->
<!--    <div id ="popup">-->
<!--      <div class="popup-header">-->
<!--        <h4>Создание очереди</h4>-->
<!--        <button id="close-btn">&times;</button>-->
<!--      </div>-->
<!--      <div class="popup-content">-->
<!--        <h5>Название & Время</h5>-->
<!--        <div class = "con6">-->
<!--          <input type="link" placeholder="Например: Джава" name="username" required>-->
<!--          <input type="text" placeholder="##:##" maxlength="5" id="time-input">-->
<!--        </div>-->
<!--        <div class = "content5">-->
<!--          <button id = "confirm">Создать очередь</button>-->
<!--        </div>-->
<!--        <h5>Скопируйте ссылку</h5>-->
<!--        <div class = "content5">-->
<!--          <button id = "copylink">🔗 Скопировать</button>-->
<!--        </div>-->
<!--      </div>-->
<!--    </div>-->

  </div>

  <div class = "content1">
    <h1>Хотите присоединиться
      к уже существующей
      очереди?</h1>
  </div>
  <div class = "content2">
    <input type="link" placeholder="Вставьте ссылку" name="username" required>
  </div>
  <div class = "content2">
    <form action="Line.html">
      <my-button class="geton">Встать в очередь</my-button>
    </form>
  </div>
</template>

<script>
import MyButton from "@/components/UI/MyButton.vue";
export default {
  name: "Home.vue",
  components: {MyButton}
}
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #ffffff;
  padding: 15px;
  top: 0;
  left: 0;
  right: 0;
}

.logo {
  font-family: 'Montserrat', sans-serif;
  font-weight: bold;
  font-size: 27px;
  color: #333333;
  text-decoration: none;
}

.circle {
  width: 39px;
  height: 39px;
  border: 2px solid #0075FF;
  border-radius: 50%;
  padding: 22px;
  box-sizing: border-box;
}
.content {
  background-color: #0075FF;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 120px 36px;
  height: auto;
}
.content1 {
  padding: 22px 38px;
  padding-bottom: 0px;
  margin-bottom: 22px;
}
.content2 {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0px 36px;
  margin-bottom: 16px;
}
.content3 {
  padding: 0px 36px;
  margin-bottom: 16px;
  height: auto;
}
h1 {
  font-family: 'Montserrat', sans-serif;
  font-weight: bold;
  font-size: 22px;
  align-self: left;
  color: #333333;
  margin-top: 0;
  margin-bottom: 0;
}
/*button[type="make"] {*/
/*  height: auto;*/
/*  width: 100%;*/

/*  color: white;*/
/*  border: 3px solid #ffffff;*/
/*  background-color: #0075FF;*/
/*  border-radius: 10px;*/
/*  font-weight: bold;*/
/*  font-size: 21px;*/
/*  padding-top: 17px;*/
/*  padding-bottom: 17px;*/
/*  margin: 0;*/
/*}*/

.make {
  color: white;
  border: 3px solid #ffffff;
  background-color: #0075FF;
}

input[type="link"] {
  border: 3px solid #0075FF;
  background-color: #ffffff;
  border-radius: 10px;
  font-weight: bold;
  padding-top: 0px;
  padding-bottom: 0px;
  height: 50px;
  padding-left: 15px;
  padding-right: 0px;
  margin: 0;
  width: 100%;
  font-size: 16px;
  font-family: "Helvetica Neue", sans-serif;
  font-weight: normal;

}

/*button[type="geton"] {*/
/*  height: auto;*/
/*  width: 100%;*/

/*  color: white;*/
/*  border: 3px solid #0075FF;*/
/*  background-color: #0075FF;*/
/*  border-radius: 10px;*/
/*  font-weight: bold;*/
/*  font-size: 21px;*/
/*  padding-top: 17px;*/
/*  padding-bottom: 17px;*/
/*  margin: 0;*/
/*}*/

.geton {
  color: white;
  border: 3px solid #0075FF;
  background-color: #0075FF;
}

form {
  width: 100%;
}
.line {
  width: 100%;
  border-bottom: 1px solid #CCCCCC;
  font: weight;
}
#time-input {
  width: 100px;
  height: 50px;
  font-family: "Montserrat", sans-serif;
  font-size: 20px;
  color: #333333;
  text-align: center;
  letter-spacing: 5px;
  border: 3px solid #0075FF;
  border-radius: 10px;
  padding: 0;
  padding-right: 0;
  padding-left: 5px;
}
.con6 {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 15px;
  margin-top: 20px;
}
</style>