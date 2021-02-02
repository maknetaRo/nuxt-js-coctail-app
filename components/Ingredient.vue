<template>
  <div class="ingredient">
    <ul>
      <li v-for="ingredient in ingredients" v-bind:key="ingredient">
        {{ ingredient }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "ingredient",
  props: ["ingredient"],
};
</script>

<style>
</style>