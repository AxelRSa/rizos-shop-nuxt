<template lang="pug">
.card
  img.card__image(:src="image", alt="altText")
  h2.card__name(:text="productName")
  .card__tag-container
    a.card__tag(href="#")(v-for="tag in tags", :key="tag.key") {{ tag }}
  .card__footer
    .card__price-container
      .card__previus-price ${{ previusPrice }}
      .card__price
        .card__actual-price ${{ price }}
        .card__discount %{{ discount }} DESC
    a.card__button(href="#")
      Cart.card__cart
</template>

<script>
export default {
  props: ["image", "productName", "tags", "previusPrice", "price", "discount"],
};
</script>

<style lang="scss" scoped>
.card {
  border-radius: 30px;
  background-color: var(--background-color);
  padding: 20px;
  width: 250px;
  border: 1px solid rgba(125, 125, 125, 0.2);
  &__image {
    height: 90px;
    width: 100%;
    object-fit: contain;
  }
  &__name {
    margin: 10px 0;
    text-align: center;
  }
  &__tag-container {
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 20px 0;
  }
  &__tag {
    padding: 2px 6px;
    font-size: 13px;
    margin: 0 5px;
    border-radius: 30px;
    background-color: var(--principal-color-v1);
    color: #fff;
    text-decoration: none;
    transition: filter 0.3s;
    text-align: center;
    &:active {
      filter: brightness(110%);
    }
  }
  &__footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__previus-price {
    font-size: 14px;
    color: var(--gray1);
    text-decoration: line-through;
  }
  &__price {
    display: flex;
  }
  &__actual-price {
    font-size: 50px;
  }
  &__discount {
    font-size: 13px;
    color: var(--principal-color);
  }
  &__button {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    background-color: var(--principal-color);
    transition: filter 0.3s;
    &:active {
      filter: brightness(110%);
    }
  }
  &__cart {
    color: #fff;
  }
}
</style>