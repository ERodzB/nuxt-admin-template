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
      <button class="flex-18col-2 btn-primary">Submit</button>
      <button class="flex-18col-2 btn-secondary">Submit</button>
      <form-text-input
        input-label="Email"
        input-requirements="Must be a correct email"
        input-name="email"
      />
      <form-combo-box />
      <form-radio-button
        radio-name="test"
        radio-label="Test"
        radio-value="test"
        radio-id="test5"
      />
      <form-radio-button
        radio-name="test"
        radio-label="Test"
        radio-value="test"
        radio-id="test4"
      />
      <form-check-box
        check-value="Somethingg"
        check-id="test10"
        check-name="test10"
        check-label="Monday"
      />
      <form-check-box
        check-value="Somethinggg"
        check-id="test11"
        check-name="test11"
        check-label="Tuesday"
      />
      <form-check-box
        check-value="Somethinggg"
        check-id="test12"
        check-name="test12"
        check-label="Wednesday"
      />
      <form-check-box
        check-value="Somethinggg"
        check-id="test13"
        check-name="test13"
        check-label="My ass hurts"
        is-checked="true"
        is-disabled="true"
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
