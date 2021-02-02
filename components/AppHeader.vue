<template>
  <header class="header">
    <h1 class="title">Cocktail Recipes</h1>
    <ul>
      <li>
        <nuxt-link to="/">Home</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/coctails">Cocktails</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/about">About</nuxt-link>
      </li>
    </ul>
  </header>
</template>

<script>
export default {
  name: "AppHeader",
};
</script>

<style>
.header {
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 100%;
}
.title {
  font-size: 2.5rem;
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  color: #35495e;
  letter-spacing: 1px;
  padding-bottom: 1rem;
  text-align: center;
}

.header ul {
  display: flex;
  align-items: center;
  padding: 0;
  justify-content: center;
}

.header li {
  list-style: none;
  justify-content: space-between;
}

.header li a {
  display: inline-block;
  text-decoration: none;
  color: white;
  background: #35495e;
  padding: 1rem;
  margin-right: 0.5rem;
  margin-left: 0.5rem;
}

@media (min-width: 600px) {
  .header {
    flex-direction: row;
    padding: 2rem 1rem;
    justify-content: space-between;
  }
}
</style>