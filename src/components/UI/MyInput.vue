<template>
  <input type="text" :value="modelValue" @input="updateInput" class="input">
</template>

<script>
export default {
 name: 'my-input',
  props: {
    modelValue: [String, Number]
  },
  methods: {
   updateInput(e){
     this.$emit('update:modelValue', e.target.value)
   }
  }
}
</script>

<style scoped>
.input{
  width: 100%;
  border: 1px solid teal;
  padding: 10px 16px;
  margin-top: 15px;
}
</style>