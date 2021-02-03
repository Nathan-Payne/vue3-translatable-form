<template>
  <header>
    <slot name="logo" class="logo"></slot>
    <section class="controls">
      <slot name="controls"></slot>
    </section>
  </header>
</template>

<script>
export default {}
</script>

<style scoped>
header {
  width: 100vw;
  height: 5rem;
  background-color: slategray;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 3rem;
}

.controls {
  width: 30vw;
  display: flex;
  justify-content: space-around;
}
</style>
