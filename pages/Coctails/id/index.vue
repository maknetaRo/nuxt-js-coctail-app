<template>
  <div>
    <nuxt-link to="/">Back to Home Page</nuxt-link>
    <h2>{{ coctail }}</h2>
    <hr />
    <small>Coctail ID: {{ $route.params.id }}</small>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      coctail: {},
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
        `https://www.thecocktaildb.com/api/json/v1/1/lookup.php?i=${this.$route.params.id}`,
        config
      );

      this.coctails = res.data.coctail;
      console.log(this.coctail);
    } catch (err) {
      console.log(err);
    }
  },
};
</script>

<style>
</style>