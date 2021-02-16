<template>
  <div class="text-input-container">
    <input
      :id="inputId"
      type="text"
      name="test"
      class="text-input-container__text-input"
      required
    />
    <label for="" class="text-input-container__text-label"
      ><awesome-icon
        name="at"
        class="text-input-container__text-label__text-icon"
      ></awesome-icon
      >{{ inputLabel }}</label
    >
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
  },
}
</script>

<style lang="scss" scoped></style>
