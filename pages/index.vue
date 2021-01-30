<template>
  <div class="container-page">
    <div class="coctail-list">
      <Coctail
        v-for="coctail in coctails"
        :key="coctail.idDrink"
        :id="coctail.idDrink"
        :title="coctail.strDrink"
        :recipe="coctail.strInstructions"
        :image="coctail.strDrinkThumb"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Coctail from "../components/Coctail";
export default {
  components: {
    Coctail,
  },
  data() {
    return {
      coctails: [],
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
        "https://www.thecocktaildb.com/api/json/v1/1/search.php?f=m",
        config
      );
      this.coctails = res.data.drinks;
      console.log(res.data.drinks);
    } catch (err) {
      console.log(err);
    }
  },
};
</script>

<style>
.coctail-list {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-around;
}
</style>