<template>
  <div class="translateOutput bor bg-light">{{translateText}}</div>
</template>

<script>
export default {
  name: "translateOutput",
  props: ["translateText"],
  data() {
    return {};
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
