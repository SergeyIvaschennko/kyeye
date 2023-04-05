<template>
  <input :value="modelValue" @input="updateInput" class="input" type="text">
</template>

<script>
export default {
  name: 'my-input',
  props: {
    modelValue: [String, Number]
  },
  methods: {
    updateInput(event) {
      this.$emit('update:modelValue', event.target.value)
    }
  }
}
</script>

<style scoped>
.input {
  border-radius: 10px;
  padding: 0 0 0 15px;
  height: 56px;
  margin: 0;
  width: 100%;
  font-size: 16px;
  font-family: "Helvetica Neue", sans-serif;
  font-weight: normal;
}

</style>