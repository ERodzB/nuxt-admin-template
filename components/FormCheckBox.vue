<template>
  <div class="check-input-container">
    <input
      :id="checkId"
      type="checkbox"
      :name="checkName"
      :value="checkValue"
      class="check-input-container__checkbox-input"
      :disabled="isDisabled"
      :checked="isChecked"
    />
    <label :for="checkId" class="check-input-container__checkbox-label"
      >{{ checkLabel }}
    </label>
    <awesome-icon name="check" class="check-input-container__check-icon" />
  </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid'
export default {
  props: {
    checkValue: {
      type: String,
      default: 'Something',
    },
    checkId: {
      type: String,
      default: uuidv4(),
    },
    checkName: {
      type: String,
      default: 'Test',
    },
    checkLabel: {
      type: String,
      default: 'Checkbox',
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
