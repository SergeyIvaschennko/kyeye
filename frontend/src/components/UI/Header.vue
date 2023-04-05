<template>
  <div class = "header">
    <a class="logo" href = "###">КУЕУЕ</a>
    <a class="circle" href = "###"></a>
  </div>
</template>

<script>
export default {
  name: "my-header"
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
</style>