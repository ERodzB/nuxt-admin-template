<template>
  <div class="text-input-container">
    <div class="text-input-container__text-icon">
      <awesome-icon :name="inputIcon"></awesome-icon>
    </div>
    <input
      :id="inputId"
      :type="inputType"
      :name="inputName"
      class="text-input-container__text-input"
      required
    />
    <label for="" class="text-input-container__text-label">{{
      inputLabel
    }}</label>
    <span class="text-input-container__text-requirements">
      {{ inputRequirements }}
    </span>
  </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid'
export default {
  props: {
    inputLabel: {
      type: String,
      default: '',
    },
    inputRequirements: {
      type: String,
      default: 'Must not be empty',
    },
    inputId: {
      type: String,
      default: uuidv4(),
    },
    inputName: {
      type: String,
      default: '',
    },
    inputType: {
      type: String,
      default: 'text',
    },
    inputIcon: {
      type: String,
      default: 'angle-right',
    },
  },
}
</script>

<style lang="scss" scoped></style>
