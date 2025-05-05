<template>
  <button>
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'my-button',
}
</script>

<style scoped>
button {
  padding: 15px 10px;
  background: none;
  color: teal;
  border: 1px solid teal;
}

</style>