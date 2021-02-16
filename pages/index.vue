<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">nuxt-admin-template</h1>
      <div class="links">
        <a
          href="https://nuxtjs.org/"
          target="_blank"
          rel="noopener noreferrer"
          class="button--green"
        >
          Documentation
        </a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          rel="noopener noreferrer"
          class="button--grey"
        >
          GitHub
        </a>
      </div>
    </div>
    <div class="flex-wrapper">
      <button class="flex-18col-2 btn-secondary">Submit</button>
      <form-text-input
        input-label="Email"
        input-requirements="Must be a correct email"
        input-name="email"
      />
    </div>
  </div>
</template>

<script>
import FormTextInput from '@/components/FormTextInput.vue'

export default {
  components: {
    FormTextInput,
  },
}
</script>

<style lang="scss">
h1 {
  color: map-get($main-theme, 'primary-color');
}
.red {
  color: red;
}
</style>
