<template>
  <div class="container">
    <h2 class="title">Bem vindo ao Jokes - sua piada estrangeira está aqui.</h2>

    <img class="image" src="../static/icon.png" alt="Smille Face" />
  </div>
</template>

<script>
export default {
  name: 'Home'
}
</script>

<style scoped>
  .container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .title {
    text-align: center;
  }

  .image {
    margin-top: 50px;
    width: 250px;
    height: 250px;
  }
</style>