<template>
  <div class="container">
    <AppHeader />
    <AlphabetList />
    <Nuxt />
  </div>
</template>

<style>
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  box-sizing: border-box;
}
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  max-width: 1200px;
  margin: 2rem auto;
  overflow: hidden;
  padding: 1rem 2rem;
  background: #fff;
}
</style>
