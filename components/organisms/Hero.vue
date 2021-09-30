<template lang="pug">
.hero
  h1.hero__display Productos<span class="hero__highlights"> profesionales </span> de belleza
  a.hero__button(
    href="https://wa.me/529984034867/?text=Hola, entré a su página web y quería tener más información",
    target="_blank"
  ) Whatsapp
    Whatsapp.hero__icon
</template>

<script>
export default {};
</script>

<style lang="scss">
.app--dark {
  .hero {
    &__display {
      background-color: initial;
    }
  }
}
.hero {
  width: 100%;
  height: 100vh;
  background: linear-gradient(
      180deg,
      rgba(var(--dinamic-background), 1) 0%,
      rgba(var(--dinamic-background), 0.4) 100%
    ),
    url("~/assets/images/background/background.png") center no-repeat fixed;

  background-size: cover;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
  &__display {
    font-size: 36px;
    line-height: 39.6px;
    text-align: center;
    color: rgb(var(--dinamic-text));
    border-radius: 20px;
    width: 300px;
    padding: 10px;
    background-color: rgba(var(--dinamic-background), 0.8);
  }
  &__highlights {
    text-transform: uppercase;
    color: rgb(var(--principal-color-700-to-prin));
  }
  &__button {
    padding: 10px 15px;
    display: flex;
    align-items: center;
    color: rgb(var(--static-background));
    text-decoration: none;
    gap: 10px;
    background-color: rgb(var(--principal-color-prin-to-700));
    border-radius: 20px;
    font-size: 20px;
  }
  &__icon {
    height: 30px;
    width: 30px;
  }
}
</style>