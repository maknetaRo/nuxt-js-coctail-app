<template>
  <nuxt-link :to="'/' + id">
    <div class="coctail">
      <h2>{{ title }}</h2>
      <Ingredient v-for="ingredient in ingredients" :key="ingredient.strId" />
      <img :src="image" />
    </div>
  </nuxt-link>
</template>

<script>
import Ingredient from "../components/Ingredient";
export default {
  name: "Coctail",
  props: ["title", "recipe", "image", "id"],
  components: {
    Ingredient,
  },
};
</script>


<style>
.coctail {
  display: grid;
  grid-template-rows: 1fr 2fr;
  grid-template-columns: fit-content(280px);
  cursor: pointer;
  border: 2px solid #35495e;
  margin: 2rem 1rem;
}

.coctail h2 {
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2.5rem;
  font-weight: 300;
  color: #35495e;
  letter-spacing: 1px;
}

a {
  text-decoration: none;
}

.coctail img {
  max-width: 100%;
}
</style>