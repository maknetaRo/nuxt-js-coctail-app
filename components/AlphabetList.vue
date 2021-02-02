<template>
  <div id="letters-row">
    <ul class="letters-list">
      <nuxt-link to="magda" v-for="letter in letters" v-bind:key="letter">
        {{ letter }}
      </nuxt-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: "alphabet-list",
  data() {
    return {
      letters: "abcdefghijklmnopqrstuvwxyz".split(""),
    };
  },
};
</script>

<style scoped>
#letters-row {
  width: 100%;
  padding-top: 1rem;
  padding-bottom: 1rem;
}
.letters-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;

  padding-left: 0;
}

li {
  list-style: none;
  cursor: pointer;
}

a {
  color: #35495e;
  font-size: 1.5rem;
  font-weight: 500;
  text-transform: uppercase;
  padding: 0.3rem 0.75rem;
  text-decoration: none;
}
a:focus,
a:hover {
  transform: scale(1.2);
  background: #35495e;
  color: white;
}
</style>