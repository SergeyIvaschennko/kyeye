<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'my-button'
}
</script>

<style scoped>
.btn {
  height: auto;
  width: 100%;

  color: white;
  border: 3px solid blue;
  background-color: blue;
  border-radius: 10px;
  font-weight: bold;
  font-size: 21px;
  padding-top: 17px;
  padding-bottom: 17px;
  margin: 0;
}

</style>