<template>
    <button type="submit">{{ text }}</button>
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

  @media (max-width: 768px) {
    padding: 2rem 1.5rem;
  }

  @media (max-width: 500px) {
    display: block;
    width: 100%;
    margin-top: 2rem;
    margin-left: 0;
  }
}
</style>
