<template>
  <nuxt-link :to="`jokes/${id}`">
    <div class="joke">
      <p>{{ joke }}</p>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: 'Joke',

  props: ['id', 'joke']
}
</script>

<style scoped>
  .joke {
    margin: 0.5rem 0;
    padding: 1rem;
    border: 1px double #ccc
  }

  .joke:hover {
    box-shadow: 0 0 5px black;
  }
</style>