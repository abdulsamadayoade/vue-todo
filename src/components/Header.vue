<template>
    <header>
        <h1>{{ title }}</h1>
    </header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    title: String
  }
}
</script>

<style lang="scss" scoped>
header {
    padding: 1.5rem 0;
    background: var(--dark);
    color: var(--text-color);
    width: 100%;
    text-align: center;
    margin-bottom: 2rem;
}

h1 {
    font-size: 2.3rem;
}
</style>
