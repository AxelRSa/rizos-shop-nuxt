<template lang="pug">
.slider(@drag="hola(e)")
  ProductCard(
    :image="require('~/assets/images/products/product1.png')",
    productName="Shampoo biohidratante con colágeno",
    :tags="['Decolorante', 'Vittalé', '350g']",
    :previusPrice="2000",
    :price="1000",
    :discount="20"
  )
  ProductCard(
    :image="require('~/assets/images/products/product1.png')",
    productName="Shampoo biohidratante con colágeno",
    :tags="['Decolorante', 'Vittalé', '350g']",
    :previusPrice="2000",
    :price="1000",
    :discount="20"
  )
  ProductCard(
    :image="require('~/assets/images/products/product1.png')",
    productName="Shampoo biohidratante con colágeno",
    :tags="['Decolorante', 'Vittalé', '350g']",
    :previusPrice="2000",
    :price="1000",
    :discount="20"
  )
</template>

<script>
export default {
  methods: {},
};
</script>

<style lang="scss" scoped>
.slider {
  width: max-content;
  display: flex;
  gap: 20px;
}
</style>