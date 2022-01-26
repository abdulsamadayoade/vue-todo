<template>
    <div class="todo">
        <div class="todo-title">
            <p>{{ todo.text }}</p>
        </div>
        <div class="todo-actions">
            <button class="todo-delete" @click="$emit('delete-todo', todo.id)">
                <i class="fas fa-times"></i>
            </button>
            <button :class="[todo.reminder ? 'active' : '', 'todo-reminder']" @click="$emit('set-reminder', todo.id)">
                <i class="far fa-bell"></i>
            </button>
        </div>
    </div>
</template>

<script>
export default {
  name: 'Todo',
  props: {
    todo: Object
  }
}
</script>

<style lang="scss" scoped>
.todo {
    display: flex;
    align-items: center;
    justify-content: space-between;
    border: 1px solid var(--text-color);
    padding: 1.5rem;
    margin-bottom: 1.5rem;

    &-actions {
        display: flex;
        align-items: center;
    }

    &-delete {
        background: var(--dark);
        color: var(--text-color);
    }

    &-reminder {
        background: var(--text-color);
        margin-left: 1rem;

        &.active {
            background: var(--dark);
            color: var(--text-color);
        }
    }
}

button {
    background: transparent;
    font-size: 2rem;
    padding: .5rem 1rem;
}
</style>
