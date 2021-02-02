<template>
  <div id="random-cocktail">
    <h2>Random Cocktail Recipe</h2>
    <RandomCocktail
      :key="random.idDrink"
      :id="random.idDrink"
      :title="random.strDrink"
      :recipe="random.strInstructions"
      :image="random.strDrinkThumb"
      :category="random.strCategory"
      :alco="random.strAlcoholic"
    />
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "random-cocktail",
  data() {
    return {
      random: [],
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json",
      },
    };
    try {
      const res = await axios.get(
        "https://www.thecocktaildb.com/api/json/v1/1/random.php",
        config
      );
      this.random = res.data.drinks[0];
      console.log(res.data.drinks[0]);
      console.log("This is random recipe");
      console.log(this.random);
    } catch (err) {
      console.log(err);
    }
  },
};
</script>

<style scoped>
h2 {
  font-size: 2.25rem;
  text-align: center;
  padding: 1rem;
  background: #35495e;
  color: white;
  margin-top: 2rem;
  margin-bottom: 2rem;
}
</style>