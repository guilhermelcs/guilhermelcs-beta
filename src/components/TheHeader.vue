<template>
  <header class="header">
    <div class="header__inner container">
      <!-- <LogoComponent class="header__logo" version="simple" desc="Main Logo" /> -->
      <g-link class="blog-title" :to="'/'">
        Guilhermelcs
      </g-link>
    </div>
  </header>
</template>

<script>
import LogoComponent from "@/components/LogoComponent.vue"
import SocialIcons from "@/components/SocialIcons.vue"

import { gsap, Sine, Power1 } from "gsap"

export default {
  components: {
    LogoComponent,
    SocialIcons
  },
  data() {
    return {
      ariaExpanded: false
    }
  },

  methods: {
    handleAriaExpanded() {
      this.ariaExpanded = !this.ariaExpanded
    }
  }
}
</script>

<style lang="scss" scoped>
.blog-title {
  margin-left: 1rem;
  font-weight: 500;
  text-decoration: none;
}

.blog-title:focus {
  outline: none;
  box-shadow: none;
}

.header {
  position: relative;
  z-index: $layer-header-z-index;
  top: 0;
  right: 0;
  left: 0;

  &__inner {
    padding-top: 1em;
    padding-bottom: 1em;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__logo {
    z-index: $layer-hamburger-z-index;
    width: 50px;
  }

  &__hamburger {
    z-index: $layer-hamburger-z-index;
  }

  &__menu {
    position: absolute;
    z-index: $layer-dropdown-z-index;
    top: 0;
    left: 0;
    visibility: hidden;
    width: 100vw;
    height: 100vh;
    background: $color-menu-gradient;
  }

  &__socialIcons {
    &--mobile {
      position: absolute;
      right: 1rem;
      bottom: 1rem;
    }
  }
}

.hamburger {
  padding: 2px;
  display: flex;
  overflow: hidden;
  width: 40px;
  height: 40px;
  flex-direction: column;
  justify-content: space-around;
  background-color: transparent;
  border: none;
  border-radius: 5px;
  transition: box-shadow $duration-animation-base linear;
  cursor: pointer;

  &__line {
    display: block;
    width: 36px;
    height: 2px;
    background-color: $color-black;
    transition: background-color $duration-animation-base linear;

    &.line01,
    &.line04 {
      width: 18px;
    }
    &.line01 {
      align-self: flex-end;
    }
  }
  &:hover {
    .hamburger__line {
      background-color: $color-primary;
    }
  }
  &:focus {
    @extend %custom-outline;
  }
}

.nav {
  position: absolute;
  top: 50%;
  left: 50%;
  overflow: hidden;

  &__list {
    margin: 0;
    padding: 2em 0.5em;
  }

  &__item {
    list-style-type: none;
    @extend %typography-xxlarge;
  }

  &__link {
    padding: 0.5em;
    text-decoration: none;
    border-radius: 5px;
  }
}

.nav .active--exact {
  text-decoration: underline;
}
</style>
