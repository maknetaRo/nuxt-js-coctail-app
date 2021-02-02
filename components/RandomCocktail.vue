<template>
  <div class="random-card">
    <div class="column column-pic">
      <img :src="image" :alt="title + ' Drink'" />
    </div>
    <div class="column column-text">
      <h2>{{ title }}</h2>
      <div class="row">
        <h3>
          Category: <span>{{ category }}</span>
        </h3>
        <h3>
          Alcoholic: <span>{{ alco }}</span>
        </h3>
      </div>
      <Ingredient />
      <p>{{ recipe }}</p>
    </div>
  </div>
</template>

<script>
import Ingredient from "./Ingredient";
export default {
  name: "random-cocktail",
  props: ["title", "recipe", "image", "id", "category", "alco"],
  components: {
    Ingredient,
  },
};
</script>

<style scoped>
.random-card {
  display: grid;
  grid-template-rows: 1fr auto;
  grid-template-columns: 1fr;
  width: 100%;
}
.column {
  display: flex;
  flex-direction: column;
  padding: 2rem 1rem;
  justify-content: center;
}

.column-pic {
  max-width: 500px;
  margin: 0 auto;
}

img {
  width: 100%;
  height: auto;
}

.row {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  padding: 1.5rem 0;
}
span {
  color: #35495e;
}
h2 {
  font-size: 2rem;
  color: #35495e;
  text-align: center;
  padding-bottom: 1.5rem;
  letter-spacing: 2px;
}
p {
  font-size: 1.25rem;
  line-height: 1.5;
}

@media screen and (min-width: 639px) {
  .random-card {
    display: grid;
    grid-template-rows: 1fr;
    grid-template-columns: 1fr 1.25fr;
    width: 100%;
  }
}
</style>
