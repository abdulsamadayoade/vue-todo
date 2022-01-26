<template>
  <input type="text" placeholder="Enter Todo" />
</template>

<script>
export default {
  name: 'TextInput'
}
</script>

<style lang="scss" scoped>
input {
    padding: 2.3rem 1.5rem;
    background: var(--text-color);
    font-size: inherit;
    color: var(--dark);
    display: inline-block;
    width: 70%;

    &::placeholder {
        color: var(--dark);
    }
}
</style>
