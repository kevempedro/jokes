<template>
  <header class="header">
    <h1 class="title">Jokes</h1>

    <ul>
      <li>
        <nuxt-link to="/">Inicial</nuxt-link>
      </li>

      <li>
        <nuxt-link to="/jokes">Piadas</nuxt-link>
      </li>

        <li>
          <nuxt-link to="/about">Sobre</nuxt-link>
        </li>
      </ul>
    </header>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style scoped>
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1rem;
    padding-bottom: 1rem;
    border-bottom: 1px double #ccc;
  }

  .header .title {
    font-size: 3rem;
    color: black;
  }

  .header ul {
    display: flex;
  }

  .header a {
    display: inline-block;
    background: black;
    color: white;
    padding: 0.3rem 1rem;
    margin-right: 0.5rem;
  }

  .header a:hover {
    background: #ccc;
    color: black;
    box-shadow: 0 0 5px black;
  }
</style>