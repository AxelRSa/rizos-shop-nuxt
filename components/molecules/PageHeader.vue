<template lang="pug">
header.header
  LogoRizoShop.header__logo
  h2.header__title {{ title }}
</template>

<script>
export default {
  props: ["title"],
};
</script>

<style lang="scss" scoped>
.header {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  position: absolute;
  top: 0;
  color: rgb(var(--dinamic-text));
  &__logo {
    width: 30px;
    height: 30px;
  }
  &__title {
    text-align: center;
    font-size: 20px;
  }
}
</style>