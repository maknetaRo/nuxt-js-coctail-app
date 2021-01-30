<template>
  <div class="ingredient">
    <p>{{ ingredient }}</p>
  </div>
</template>

<script>
export default {
  name: "Ingredient",
  props: ["ingredient", "id"],
};
</script>

<style>
</style>