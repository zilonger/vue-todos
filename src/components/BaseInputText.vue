<template>
  <input type="text" placeholder="New todo" class="input" :value="value" v-on="listeners">
</template>

<script>
    export default {
      props: {
        value: {
          type: String,
          default: ''
        }
      },
      computed: {
        listeners () {
          // debugger
          return {
            ...this.$listeners,
            input: event => this.$emit('input', event.target.value)
          }
        }
      }
    }
</script>

<style scoped>
  .input {
    width: 100%;
    padding: 8px 10px;
    border: 1px solid #32485F;
  }
</style>
