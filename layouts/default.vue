<template>
  <div class="main-app jsb">
    <div class="main-app__side-menu"></div>
    <Nuxt class="main-app__content" />
  </div>
</template>

<style lang="scss">
.main-app {
  @extend %flex-wrapper;
  @extend %h-100-vh;
  &__side-menu {
    @extend %flex-18col-4;
    background-color: $blue-100;
  }
  &__content {
    @extend %flex-18col-13;
    background-color: map-get($map: $main-theme, $key: 'background-color');
  }
}
</style>
