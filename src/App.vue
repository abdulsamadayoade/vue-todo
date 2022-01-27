<template>
  <Header title="Todo App" />
  <AddTodo @add-todo="addTodo" />
  <Todos :todos="todos" @delete-todo="deleteTodo" @set-reminder="setReminder" />
  <p v-if="todos.length > 0">Click the bell icon to toggle reminder.</p>
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
    addTodo (newTodo) {
      this.todos = [...this.todos, newTodo]
    },
    deleteTodo (id) {
      this.todos = this.todos.filter((todo) => todo.id !== id)
    },
    setReminder (id) {
      this.todos = this.todos.map((todo) => todo.id === id ? { ...todo, reminder: !todo.reminder } : todo)
    }
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
