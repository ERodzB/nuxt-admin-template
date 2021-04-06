<template>
  <div class="main-app jsb">
    <div class="main-app__side-menu"></div>
    <div class="main-app__main-display">
      <div class="main-app__main-display__top-menu"></div>
      <Nuxt class="main-app__main-display__content" />
    </div>
  </div>
</template>

<style lang="scss">
.main-app {
  @extend %flex-wrapper;
  min-height: 100vh;
  overflow: auto;
  &__side-menu {
    @extend %flex-18col-4;
    position: sticky;
    top: 0;
    background-color: $blue-100;
  }
  &__main-display {
    @extend %flex-18col-13;
    margin: 20px 20px 0px 20px;
    background-color: map-get($map: $main-theme, $key: 'background-color');
    &__top-menu {
      height: 60px;
      width: 100%;
      background-color: map-get($map: $main-theme, $key: 'primary-color');
    }
    &__content {
      height: 200%;
      width: 100%;
      border-radius: 20px;
      background-color: map-get(
        $map: $main-theme,
        $key: 'form-background-color'
      );
    }
  }
}
</style>
