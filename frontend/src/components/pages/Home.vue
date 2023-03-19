<template>
  <div class = "header">
    <div class="logo">КУЕУЕ</div>
    <a class="circle" href = "index.html"></a>
  </div>
  <div class = "content">

    <button type="make" id = "popup-btn">Создать очередь</button>
    <div id="modal-background"></div>
    <div id ="popup">
      <div class="popup-header">
        <h4>Создание очереди</h4>
        <button id="close-btn">&times;</button>
      </div>
      <div class="popup-content">
        <h5>Название & Время</h5>
        <div class = "con6">
          <input type="link" placeholder="Например: Джава" name="username" required>
          <input type="text" placeholder="##:##" maxlength="5" id="time-input">
        </div>
        <div class = "content5">
          <button id = "confirm">Создать очередь</button>
        </div>
        <h5>Скопируйте ссылку</h5>
        <div class = "content5">
          <button id = "copylink">🔗 Скопировать</button>
        </div>
      </div>
    </div>

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
      <button type="geton">Встать в очередь</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "Home.vue"

}
</script>

<style scoped>

</style>