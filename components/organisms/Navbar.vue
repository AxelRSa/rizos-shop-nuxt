<template lang="pug">
.nav
  nav.nav__icons
    .nav__icon: ArrowTop
    NuxtLink.nav__icon(to="/carrito-de-compras"): Cart
    .nav__icon(@click="toggleMenu()")
      transition(name="fade")
        Menu.nav__menu(v-show="!MenuState")
      transition(name="fade") 
        Close.nav__menu(v-show="MenuState")
  transition(name="fade")
    nav.nav__links(v-show="MenuState", @click="closeMenu()")
      NuxtLink.nav__logo(to="/"): LogoRizoShop
      button.nav__toggle-theme(@click="changeTheme()")
        .nav__toggle(:class="{ 'nav__toggle--left': theme }")
          Moon.nav__toggle-icon(v-if="theme")
          Sun.nav__toggle-icon(v-if="!theme")
      NuxtLink.nav__link(to="/") Inicio
      NuxtLink.nav__link(to="/productos") Productos
      NuxtLink.nav__link(to="/contacto") Contacto
      NuxtLink.nav__link(to="/sobre-nosotros") Sobre nosotros
      NuxtLink.nav__link(to="/marcas") Marcas
</template>
<script>
export default {
  props: ["theme"],
  data() {
    return {
      MenuState: false,
    };
  },
  methods: {
    toggleMenu() {
      this.MenuState = !this.MenuState;
    },
    closeMenu() {
      setTimeout(() => {
        this.MenuState = false;
      }, 500);
    },
    changeTheme() {
      if (localStorage.theme === "dark") {
        localStorage.theme = "light";
      } else {
        localStorage.theme = "dark";
      }
      this.$emit("emitDefaultChangeTheme");
    },
  },
};
</script>
<style lang="scss" scoped>
.nav {
  z-index: 1000;
  position: relative;
  &__icons {
    position: fixed;
    bottom: 0;
    height: 35px;
    z-index: 100;
    width: 100%;
    background-color: rgb(var(--principal-color-prin-to-700));
    display: flex;
    justify-content: space-around;
    align-items: center;
    transition: background-color 0.3s;
  }
  &__icon {
    width: 30px;
    height: 30px;
    padding: 2px;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 50%;
    transition: background-color 0.3s;
    color: rgb(var(--static-background));
    position: relative;
    &:active {
      background-color: #8a8a8a77;
    }
  }
  &__menu {
    position: absolute;
    top: 0;
    left: 0;
    padding: 2px;
  }
  &__links {
    position: fixed;
    height: 100vh;
    width: 100vw;
    top: 0;
    left: 0;
    padding: 30px 0 30px 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-evenly;
    background-color: rgb(var(--dinamic-background));
    transition: background-color 0.5s;
  }
  &__logo {
    position: absolute;
    top: 20px;
    left: 20px;
    width: 30px;
    height: 30px;
    color: rgb(var(--dinamic-text));
    transition: color 0.5s;
  }
  &__toggle-theme {
    position: absolute;
    top: 20px;
    right: 20px;
    border: none;
    border-radius: 20px;
    background-color: #7b7b7b;
    width: 50px;
    height: 30px;
  }
  &__toggle {
    position: absolute;
    background-color: #001fc2;
    height: 30px;
    width: 30px;
    display: flex;
    align-items: center;
    justify-content: center;
    top: 0;
    left: 0;
    border-radius: 50%;
    transition: left 0.3s;
    &--left {
      left: calc(100% - 30px);
    }
  }
  &__toggle-icon {
    width: 20px;
    height: 20px;
  }
  &__link {
    text-decoration: none;
    font-size: 35px;
    color: rgb(var(--dinamic-text));
    transition: color 0.5s;
    width: 100%;
    text-align: center;
    padding: 10px 0;
    position: relative;
    &::before {
      z-index: -1;
      content: "";
      position: absolute;
      bottom: 0;
      left: -10%;
      height: 100%;
      background-color: rgb(var(--principal-color-prin-to-700));
      width: 0;
      transition: width 0.5s;
      border-radius: 20px;
    }
  }
}
.fade-enter {
  opacity: 0;

  &-active {
    transition: opacity 0.3s;
  }
  &-to {
    opacity: 1;
  }
}

.fade-leave {
  opacity: 1;

  &-active {
    transition: opacity 0.3s;
  }
  &-to {
    opacity: 0;
  }
}
.nav__link.nuxt-link-exact-active {
  color: rgb(var(--static-background));
  &::before {
    width: 120%;
  }
}
</style>