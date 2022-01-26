<template>
  <section>
    <TextInput />
    <Button text="Add Todo" />
  </section>
</template>

<script>
import Button from './Button.vue'
import TextInput from './TextInput.vue'
export default {
  name: 'AddTodo',
  components: {
    Button,
    TextInput
  }
}
</script>

<style lang="scss" scoped>
  section {
    margin-bottom: 4rem;
  }
</style>
