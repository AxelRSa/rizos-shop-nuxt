<template lang="pug">
.card
  img.card__image(:src="image", alt="altText")
  h2.card__name {{ productName }}
  .card__tag-container
    a.card__tag(href="#", v-for="tag in tags", :key="tag.key") {{ tag }}
  .card__footer
    .card__price-container
      .card__previus-price ${{ previusPrice }}
      .card__price
        .card__actual-price ${{ price }}
        .card__discount %{{ discount }} DESC
    a.card__button(href="#")
      IconCart.card__cart
</template>

<script>
export default {
  props: {
    image: String,
    productName: String,
    tags: Array,
    previusPrice: Number,
    price: Number,
    discount: Number,
  },
};
</script>

<style lang="scss" scoped>
.card {
  border-radius: 30px;
  background-color: var(--background-color);
  padding: 15px;
  width: 250px;
  border: 1px solid rgba(var(--gray-1), 0.5);
  display: flex;
  flex-direction: column;
  gap: 15px;
  &__image {
    height: 90px;
    width: 100%;
    object-fit: contain;
  }
  &__name {
    text-align: center;
    font-size: 16px;
  }
  &__tag-container {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
    gap: 5px;
  }
  &__tag {
    padding: 4px 8px;
    font-size: 13px;
    border-radius: 30px;
    background-color: rgba(var(--principal-color-700));
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
    color: rgba(var(--gray-1));
    text-decoration: line-through;
  }
  &__price {
    display: flex;
  }
  &__actual-price {
    font-size: 35px;
  }
  &__discount {
    font-size: 12px;
    color: rgba(var(--principal-color));
  }
  &__button {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    background-color: rgba(var(--principal-color));
    transition: filter 0.3s;
    padding: 10px;
    &:active {
      filter: brightness(110%);
    }
  }
  &__cart {
    color: rgba(var(--static-background));
  }
}
</style>