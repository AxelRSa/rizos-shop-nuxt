<template lang="pug">
.ofertas
  NuxtLink.ofertas__header.section-header(to="/productos")
    h2.ofertas__h2.section-header__h2 Ofertas
    LinkIcon.ofertas__icon.section-header__icon
  ProductSlider
</template>

<script>
export default {};
</script>

<style lang="scss">
.ofertas {
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