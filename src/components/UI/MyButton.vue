<template>
  <button
      class="btn">
    <slot>
    </slot>
  </button>
</template>

<script>
export default {
  name: "my-button",
}
</script>

<style scoped>
.btn {
  align-self: flex-end;
  padding: 10px 15px;
  border: 3px solid cornflowerblue;
  background: none;
  color: cornflowerblue;
  border-radius: 5px;
}
</style>