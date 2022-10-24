<template>
  <button>{{ label }}</button>
</template>
  
<script>
export default {
  props: {
    label: String,
  },
}
</script>

<style scoped>
button {
  border-radius: .4rem;
  font-size: 1rem;
  padding: .5rem 1rem;
  background: var(--profitroles-color);
  color: white;
  border: none;
  font-weight: 600;
}

button:hover {
  background: #bb0000;
}

button[disabled] {
  background: lightgray;
}
</style>