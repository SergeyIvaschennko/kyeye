<template>
  <link href="https://fonts.googleapis.com/css?family=Montserrat:900" rel="stylesheet">
  <link href='https://fonts.googleapis.com/css?family=Montserrat:Bold,700' rel='stylesheet'>
  <my-header></my-header>
  <div class = "content">

    <my-button class="create">Создать очередь</my-button>
<!--    <div id="modal-background"></div>-->
<!--    <div id ="popup">-->
<!--      <div class="popup-header">-->
<!--        <h4>Создание очереди</h4>-->
<!--        <button id="close-btn">&times;</button>-->
<!--      </div>-->
<!--      <div class="popup-content">-->
<!--        <h5>Название & Время</h5>-->
<!--        <div class = "con6">-->
<!--          <my-input class="link" placeholder="Например: Джава"></my-input>-->
<!--          <input type="text" placeholder="##:##" maxlength="5" id="time-input">-->
<!--        </div>-->
<!--        <div class = "content5">-->
<!--          <my-button class="make">Создать очередь</my-button>-->
<!--        </div>-->
<!--        <h5>Скопируйте ссылку</h5>-->
<!--        <div class = "content5">-->
<!--          <my-button class="copylink">🔗 Скопировать</my-button>-->
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
    <my-input class="link" placeholder="Вставьте ссылку"></my-input>
  </div>
  <div class = "content2">
    <form action="###">
      <my-button class="geton">Встать в очередь</my-button>
    </form>
  </div>
</template>

<script>
import MyButton from "@/components/UI/MyButton.vue";
import MyInput from "@/components/UI/MyInput.vue";
import MyHeader from "@/components/UI/Header.vue";
export default {
  name: "Home.vue",
  components: {MyHeader, MyButton, MyInput}
}
</script>

<style scoped>
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
  align-self: flex-start;
  color: #333333;
  margin-top: 0;
  margin-bottom: 0;
}

.create {
  color: white;
  border: 3px solid #FFFFFF;
  background-color: #0075FF;
}

.make {
  color: white;
  border: 3px solid #0075FF;
  background-color: #0075FF;
}

.link {
  border: 3px solid #0075FF;
  background-color: #ffffff;
}

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
}
#time-input {
  width: 111px;
  height: 56px;
  font-family: "Montserrat", sans-serif;
  font-size: 20px;
  color: #333333;
  text-align: center;
  letter-spacing: 5px;
  border: 3px solid #0075FF;
  border-radius: 10px;
  padding: 0 0 0 5px;
}
.con6 {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 15px;
  margin-top: 20px;
}






#popup {
  z-index: 2;
  position: fixed;
  bottom: 0px;
  left: 3px;
  right: 3px;

  height: 80%;
  background-color: #ffffff;
  border-top-left-radius: 20px;
  border-top-right-radius: 20px;
  overflow: hidden;
  transition: height 0.5s ease-in-out;
}

#popup.active {
  height: 80%;
}

.popup-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 20px;
  background-color: #0d74f6;
  border-top-left-radius: 20px;
  border-top-right-radius: 20px;
}

.popup-header h2 {
  font-size: 24px;
  margin: 0;
}

#close-btn {
  background-color: transparent;
  color: white;
  border: none;
  font-size: 30px;
  cursor: pointer;
  padding: 1px 0px;
}

.popup-content {
  padding: 20px;
}


#modal-background {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 1;
  background: rgba(204, 204, 204, 0.5);
  -webkit-backdrop-filter: blur(5px);
  backdrop-filter: blur(5px);
  display: none;
}

h4 {
  font-family: 'Montserrat', sans-serif;
  font-weight: bold;
  font-size: 22px;
  align-self: left;
  color: #ffffff;
  margin-top: 0;
  margin-bottom: 0;
}

h5 {
  font-family: 'Montserrat', sans-serif;
  font-weight: bold;
  font-size: 22px;
  align-self: left;
  color: #333333;
  margin-top: 0;
  margin-bottom: 0;
}

.content5 {
  margin-top: 15px;
  display: flex;
  padding: 0;
  align-items: center;
  margin-bottom: 20px;
  justify-content: space-between;
}

#confirm {
  height: 60px;
  width: 100%;
  cursor: pointer;
  color: white;
  border: 3px solid #0e75f6;
  background-color: #0e75f6;
  border-radius: 10px;
  font-weight: bold;
  font-size: 18px;
  margin: 0;
}

#confirm.clicked {
  padding-top: 3px;
}

.copylink {
  color: white;
  border: 3px solid #333333;
  background-color: #333333;
}

#copylink.clicked {
  border: 3px solid #333333;
  background-color: #333333;
}




</style>