<template>
  <div class="main-app jsb">
    <app-main-menu
      class="main-app__side-menu"
      :menu-links="[
        {
          title: 'MANAGEMENT',
          links: [
            { route: '#', name: 'Inventory', icon: 'warehouse' },
            { route: '#', name: 'Orders', icon: 'truck-loading' },
            { route: '#', name: 'Categories', icon: 'list' },
          ],
        },
        {
          title: 'SECURITY',
          links: [
            { route: '#', name: 'Users', icon: 'users' },
            { route: '#', name: 'Roles', icon: 'users-cog' },
            { route: '#', name: 'Access', icon: 'user-lock' },
          ],
        },
      ]"
    />
    <div class="main-app__main-display">
      <div class="main-app__main-display__top-menu"></div>
      <Nuxt class="main-app__main-display__content" />
    </div>
  </div>
</template>

<script>
import AppMainMenu from '~/components/AppMainMenu.vue'
export default {
  components: { AppMainMenu },
}
</script>

<style lang="scss">
.main-app {
  @extend %flex-wrapper;
  min-height: 100vh;
  overflow: auto;
  &__side-menu {
    @extend %flex-20col-4;
    position: sticky;
    top: 0px;
    left: -5px;
    bottom: 0px;
    padding: 40px;
    background-color: $blue-100;
    height: 100vh;
    overflow-y: auto;
    &* {
      widows: 100%;
    }
    h3 {
      text-align: center;
      color: map-get($map: $main-theme, $key: 'inverted-text-color');
    }
  }
  &__main-display {
    @extend %flex-20col-15;
    margin: 20px 20px 0px 20px;
    background-color: map-get($map: $main-theme, $key: 'background-color');
    &__top-menu {
      height: 60px;
      margin: 0px 0px 50px 0px;
      width: 100%;
      background-color: map-get($map: $main-theme, $key: 'primary-color');
    }
    &__content {
      height: 200%;
      width: 100%;
      padding: 8px 0px 0px 0px;
      border-radius: 20px;
      background-color: map-get(
        $map: $main-theme,
        $key: 'form-background-color'
      );
    }
  }
}
</style>
