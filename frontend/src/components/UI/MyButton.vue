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
  width: 100%;
  color: white;
  border-radius: 10px;
  font-weight: bold;
  font-size: 18px;
  height: 60px;
  margin: 0;
}

</style>