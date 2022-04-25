<template>
  <div class="card">
    <p>{{ fact }}</p>
  </div>
</template>

<script>
export default {
  name: 'FactComponent',
  props: {
    fact: {
      type: String,
      default: 'Annecdote'
    }
  }
}
</script>

<style scoped>
.card {
  border: 1px solid red;
  width: 80vw;
  margin: 0 auto;
  margin-top: 10px;
}
</style>