<template>
  <div class = "content1">
    <div class = "bluebox">
      <h2><slot name="type"></slot></h2>
    </div>
    <div class = "whitebox">
      <h3><slot name="user"></slot></h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "BoxUserInLine"
}
</script>

<style scoped>
.content1 {
  margin-bottom: 32px;
  margin-top: 20px;
  height: 153px;
  position: relative;
}
.bluebox {
  padding-top: 13px;
  height: 120px;
  top: 0;
  left: 0;
  right: 10px;
  background-color: #0075FF;
  border-radius: 5px;
  position: absolute;
}
.whitebox {
  position: absolute;
  top: 49px;
  right: 0;
  left: 20px;
  border: 2px solid #0075FF;
  height: 100px;
  background-color: #ffffff;
  border-radius: 5px;
  display: flex;
  align-items: center;
  padding-left: 22px;
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
</style>