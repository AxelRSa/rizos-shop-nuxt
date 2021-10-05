<template lang="pug">
.ofertas
  NuxtLink.ofertas__header.section-header(to="/productos")
    h2.ofertas__h2.section-header__h2 Ofertas
    IconLink.ofertas__icon.section-header__icon
  ProductCardSlider
</template>

<script>
export default {};
</script>

<style lang="scss">
.ofertas {
  display: flex;
  flex-direction: column;
  gap: 20px;
  padding: 20px;
  &__header {
    display: flex;
    gap: 10px;
    align-items: center;
  }
  &__h2 {
    color: rgb(var(--dinamic-text));
  }
  &__icon {
    color: rgb(var(--principal-color));
  }
}
</style>