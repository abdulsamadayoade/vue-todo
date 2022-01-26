<template>
  <Header title="Todo App" />
  <AddTodo />
  <Todos :todos="todos" @delete-todo="deleteTodo" @set-reminder="setReminder" />
</template>

<script>
import Header from './components/Header.vue'
import AddTodo from './components/AddTodo.vue'
import Todos from './components/Todos'
export default {
  components: {
    Header,
    AddTodo,
    Todos
  },
  data () {
    return {
      todos: []
    }
  },
  methods: {
    deleteTodo (id) {
      this.todos = this.todos.filter((todo) => todo.id !== id)
    },
    setReminder (id) {
      this.todos = this.todos.map((todo) => todo.id === id ? { ...todo, reminder: !todo.reminder } : todo)
    }
  },
  created () {
    this.todos = [
      {
        id: 1,
        text: 'Learn VueJS',
        day: 'Jan 26th at 9:00am',
        reminder: true
      },
      {
        id: 2,
        text: 'Walk the dog',
        day: 'Jan 28th at 1:20pm',
        reminder: false
      },
      {
        id: 3,
        text: 'Call Mum',
        day: 'Jan 30th at 1:20pm',
        reminder: true
      }
    ]
  }
}
</script>

<style lang="scss">
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin: 0 auto;
  width: 500px;
}
</style>
