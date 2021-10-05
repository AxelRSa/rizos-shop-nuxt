<template lang="pug">
.app(:class="{ 'app--dark': theme }")
  TheNavbar(@emitDefaultChangeTheme="emitChangeTheme", :theme="theme")
  Nuxt
</template>

<script>
export default {
  data() {
    return {
      theme: false,
    };
  },
  mounted() {
    if (localStorage.theme) {
      localStorage.theme === "dark"
        ? (this.theme = true)
        : (this.theme = false);
    } else {
      if (
        window.matchMedia &&
        window.matchMedia("(prefers-color-scheme: dark)").matches
      ) {
        this.theme = true;
        localStorage.theme = "dark";
      }
      if (
        window.matchMedia &&
        window.matchMedia("(prefers-color-scheme: light)").matches
      ) {
        this.theme = false;
        localStorage.theme = "light";
      }
    }
  },
  methods: {
    emitChangeTheme() {
      localStorage.theme === "dark"
        ? (this.theme = true)
        : (this.theme = false);
    },
  },
};
</script>

<style lang="scss">
.app {
  // static colors
  --static-text: 0, 0, 0;
  --static-background: 255, 255, 255;
  --principal-color: 76, 175, 80;
  --principal-color-700: 46, 125, 50;
  --gray-1: 130, 130, 130;
  // dinamic colors
  --dinamic-text: 0, 0, 0;
  --dinamic-background: 255, 255, 255;
  --principal-color-prin-to-700: 76, 175, 80;
  --principal-color-700-to-prin: 46, 125, 50;

  // css
  background-color: rgb(var(--dinamic-background));
  color: rgb(var(--dinamic-text));
  overflow-x: hidden;
  // dark theme
  &--dark {
    --dinamic-text: 255, 255, 255;
    --dinamic-background: 0, 0, 0;
    --principal-color-prin-to-700: 46, 125, 50;
    --principal-color-700-to-prin: 76, 175, 80;
  }
}
</style>