<template lang="pug">
.slider(@dragover.prevent="", @drop.prevent="drop")
  ProductCard
</template>

<script>
export default {
  methods: {
    drop(e) {
      console.log(e);
    },
  },
};
</script>

<style lang="scss" scoped>
</style>