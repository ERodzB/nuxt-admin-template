<template>
  <div class="radio-input-container">
    <input
      :id="radioId"
      type="radio"
      :name="radioName"
      :value="radioValue"
      class="radio-input-container__radio-input"
      :disabled="isDisabled"
      :checked="isChecked"
    />
    <label :for="radioId" class="radio-input-container__input-label">
      {{ radioLabel }}</label
    >
    <div class="radio-input-container__radio-icon"></div>
  </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid'

export default {
  props: {
    radioLabel: {
      type: String,
      default: '',
    },
    radioId: {
      type: String,
      default: uuidv4(),
    },
    radioName: {
      type: String,
      default: '',
    },
    radioValue: {
      type: String,
      default: '',
    },
    isDisabled: {
      type: Boolean,
      default: false,
    },
    isChecked: {
      type: Boolean,
      default: false,
    },
  },
}
</script>

<style lang="scss" scoped></style>
