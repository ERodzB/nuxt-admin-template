<template>
  <div class="main-menu">
    <div class="main-menu__menu-header">
      <img src="~/static/foto.png" alt="Profile Picture" />
      <h5>{{ userData.name }}</h5>
      <p>{{ userData.role.toUpperCase() }}</p>
      <div class="main-menu__menu-header__line"></div>
    </div>
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
            <p>{{ link.name.toUpperCase() }}</p>
          </a>
        </div>
      </div>
      <div class="main-menu__links__menu-logout">
        <a href="#" class="main-menu__links__menu-logout__menu-link d-flex aic">
          <span><awesome-icon scale="1.2" name="sign-out-alt" /></span>LOGOUT
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
    userData: {
      type: Object,
      default: () => ({
        name: 'Eric Rodriguez',
        role: 'Administrator',
      }),
    },
  },
}
</script>

<style lang="scss" scoped>
.main-menu {
  &__menu-header {
    font-family: $bodyFontFamily;
    height: 22%;
    text-align: center;
    width: 100%;
    padding: 0px 4px 0px 0px;
    img {
      height: 100px;
      width: 100px;
      border-radius: 100%;
      object-fit: cover;
    }
    h5 {
      font-family: $bodyFontFamily;
      color: $grey-900;
      margin: 0px 0px 4px 0px;
    }
    p {
      color: $grey-600;
    }
    &__line {
      width: 100%;
      height: 2px;
      background-color: $grey-800;
      margin: 12px 0px;
    }
  }
  &__links {
    height: 78%;
    &__content {
      margin: 40px 0px 0px 0px;
      &__container {
        &__menu-link-title {
          color: $grey-900;
          font-family: $bodyFontFamily;
          margin: 4px 0px;
        }
        &__menu-link {
          span {
            margin: 0px 24px 0px 0px;
          }
          color: $grey-900;
          margin: 8px 0px;
          font-size: $xs-title-text;
          width: 100%;
        }
      }
    }

    &__menu-logout {
      &__menu-link {
        span {
          margin: 0px 24px 0px 0px;
        }
        margin: 6px 0px;
        color: $grey-900;
        font-size: $xs-title-text;
      }
    }
  }
}
</style>
