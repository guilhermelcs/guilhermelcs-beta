<template>
  <footer class="footer">
    <div class="footer__inner container">
      <p class="blog-name-footer">Guilhermelcs</p>

      <div class="footer__socialIcons">
        <SocialIcons parent-component="the Footer" />
      </div>
    </div>
  </footer>
</template>

<script>
import LogoComponent from "@/components/LogoComponent.vue"
import SocialIcons from "@/components/SocialIcons.vue"

export default {
  components: {
    LogoComponent,
    SocialIcons
  },
  data() {
    return {
      thisYear: new Date().getFullYear()
    }
  }
}
</script>

<style lang="scss" scoped>
.footer {
  @extend %skewBorderBeforeFlip;
  padding-top: 85px;
  display: flex;
  justify-content: center;
  color: $color-text-alt2;
  background-color: $color-body-bg-alt;

  &__logo {
    margin: 0 auto 17px;
    display: block;
    width: 160px;
  }

  &__copyright {
    text-align: center;

    a {
      color: $color-text-alt2;
      &:hover {
        color: $color-primary;
      }
    }
  }

  &__inner {
    text-align: center;
  }
}

.blog-name-footer {
  display: inline-block;
  color: $color-white;
  &:hover {
    color: $color-primary;
  }
}
</style>
