<template>
  <div v-for="todo in todos" :key="todo.id" >
    <Todo :todo="todo" @delete-todo="$emit('delete-todo', todo.id)" @set-reminder="$emit('set-reminder', todo.id)" />
  </div>
</template>

<script>
import Todo from './Todo.vue'
export default {
  name: 'Todos',
  props: {
    todos: Array
  },
  components: {
    Todo
  },
  data () {
    return {
      tasks: []
    }
  },
  emits: ['delete-todo', 'set-reminder']
}
</script>

<style lang="scss" scoped>

</style>
