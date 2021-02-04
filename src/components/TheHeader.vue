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
  position: fixed;
  width: 100vw;
  min-height: 5rem;
  background-color: whitesmoke;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-direction: column;
  padding: 1rem 3rem;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1),
    0 2px 4px -1px rgba(0, 0, 0, 0.06);
}

.controls {
  width: 50vw;
  display: flex;
  justify-content: space-around;
  flex-direction: column;
}

@media (min-width: 768px) {
  header {
    flex-direction: row;
  }
  .controls {
    width: 40vw;
    flex-direction: row;
  }
}
@media (min-width: 1100px) {
  .controls {
    width: 30vw;
  }
}
</style>
