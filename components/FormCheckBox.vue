<template>
  <div class="check-input-container">
    <input
      :id="checkId"
      type="checkbox"
      :name="checkName"
      :value="checkValue"
      class="check-input-container__checkbox-input"
    />

    <label :for="checkId" class="check-input-container__checkbox-label"
      >{{ checkLabel }}
    </label>
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
  },
}
</script>

<style lang="scss" scoped></style>
