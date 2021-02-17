<template>
  <div class="combo-input-container">
    <select
      id=""
      name=""
      class="combo-input-container__combobox"
      @change="selectTouched"
    >
      <option
        v-if="isTouched == false"
        value=""
        class="combo-input-container__combobox__item"
      >
        {{ comboLabel }}
      </option>
      <option value="test">test</option>
    </select>
  </div>
</template>

<script>
export default {
  props: {
    comboLabel: {
      type: String,
      default: 'Select an option',
    },
  },
  methods: {
    selectTouched() {
      return (this.isTouched = true)
    },
  },
  data() {
    return {
      isTouched: false,
    }
  },
}
</script>

<style lang="scss" scoped></style>
