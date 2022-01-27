<template>
  <section>
    <form @submit="submitTodo">
      <div>
        <TextInput v-model:textValue="todoTitle" />
        <Button text="Add Todo" />
      </div>
      <div class="reminder-label">
        <input id="reminder" type="checkbox" v-model="reminder" name="reminder" />
        <label for="reminder">Set reminder for this todo</label>
      </div>
    </form>
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
  },
  data () {
    return {
      todoTitle: '',
      reminder: false
    }
  },
  methods: {
    submitTodo (e) {
      e.preventDefault()
      if (!this.todoTitle) {
        alert('Please fill in your todo')
      }

      const newTodo = {
        id: Math.random(),
        text: this.todoTitle,
        reminder: this.reminder
      }

      this.$emit('add-todo', newTodo)

      this.todoTitle = ''
      this.reminder = false
    }
  }
}
</script>

<style lang="scss" scoped>
  section {
    margin-bottom: 3rem;
  }

  .reminder-label {
    margin-top: 1rem;
    display: flex;
    align-items: center;

    label {
      margin-left: 1rem;
    }
  }
</style>
