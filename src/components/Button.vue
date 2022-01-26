<template>
    <button>{{ text }}</button>
</template>

<script>
export default {
  name: 'Button',
  props: {
    text: String
  }
}
</script>

<style lang="scss" scoped>
button {
    font-size: 14px;
    font-weight: var(--dark);
    font-weight: var(--fw-600);
    text-transform: uppercase;
    letter-spacing: 1.3px;
    padding: 2.3rem 1.5rem;
    background: rgb(112,137,65);
    color: var(--text-color);
    width: 28%;
    margin-left: 2%;
    border-color: transparent;
}
</style>
