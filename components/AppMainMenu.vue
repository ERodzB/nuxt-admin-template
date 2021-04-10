<template>
  <div class="main-menu">
    <h3 class="main-menu__menu-title">Nuxt Template</h3>
    <div class="main-menu__links d-flex flex-column jsb">
      <div class="main-menu__links__content">
        <div
          v-for="content in menuLinks"
          :key="content.title"
          class="main-menu__links__content__container d-flex flex-column"
        >
          <h5 class="main-menu__links__content__container__menu-link-title">
            {{ content.title }}
          </h5>

          <a
            v-for="link in content.links"
            :key="link.route"
            :href="link.route"
            class="main-menu__links__content__container__menu-link d-flex aib"
          >
            <span><awesome-icon scale="1.3" :name="link.icon" /></span>
            {{ link.name }}</a
          >
        </div>
      </div>
      <div class="main-menu__links__menu-logout">
        <a href="#" class="main-menu__links__menu-logout__menu-link d-flex aib">
          <span><awesome-icon scale="1.3" name="sign-out-alt" /></span>Logout
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    menuLinks: {
      type: Array,
      default: () => [{}],
    },
  },
}
</script>

<style lang="scss" scoped>
.main-menu {
  &__menu-title {
    font-family: $bodyFontFamily;
    height: 15%;
  }
  &__links {
    height: 85%;
    &__content {
      &__container {
        &__menu-link-title {
          font-family: $bodyFontFamily;
          margin: 18px 0px 14px 0px;
          color: map-get($map: $main-theme, $key: 'inverted-text-color');
        }
        &__menu-link {
          span {
            margin: 0px 14px 0px 0px;
          }
          margin: 10px 0px;
          color: $grey-500;
          font-size: $xs-title-text;
          width: 100%;
        }
      }
    }

    &__menu-logout {
      &__menu-link {
        span {
          margin: 0px 14px 0px 0px;
        }
        margin: 6px 0px;
        color: map-get($map: $main-theme, $key: 'inverted-text-color');
        font-size: $xs-title-text;
      }
    }
  }
}
</style>
