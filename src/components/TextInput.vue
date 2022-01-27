<template>
  <input :value="textValue" @input="$emit('update:textValue', $event.target.value)" type="text" placeholder="Enter Todo" />
</template>

<script>
export default {
  name: 'TextInput',
  props: ['textValue'],
  emits: ['update:textValue']
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

  @media (max-width: 768px) {
    padding: 2rem 1.5rem
  }

  @media (max-width: 500px) {
    display: block;
    width: 100%;
  }
}
</style>
