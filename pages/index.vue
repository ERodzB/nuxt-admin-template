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
      <!-- <button class="flex-18col-2 btn-secondary">Submit</button> -->
      <form-text-input
        input-label="Email"
        input-requirements="Must be a correct email"
        input-name="email"
      />
      <form-combo-box />
      <form-radio-button
        radio-name="test"
        radio-label="test"
        radio-value="test"
        radio-id="test5"
      />
      <form-radio-button
        radio-name="test"
        radio-label="test"
        radio-value="test"
        radio-id="test4"
      />
    </div>
  </div>
</template>

<script>
import FormTextInput from '@/components/FormTextInput.vue'
import FormComboBox from '~/components/FormComboBox.vue'
import FormRadioButton from '~/components/FormRadioButton.vue'

export default {
  components: {
    FormTextInput,
    FormComboBox,
    FormRadioButton,
  },
}
</script>

<style lang="scss">
.container {
  padding: 10px;
}
h1 {
  color: map-get($main-theme, 'primary-color');
}
.red {
  color: red;
}
</style>
