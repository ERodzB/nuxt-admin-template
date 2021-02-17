<template>
  <div class="combo-input-container">
    <select
      id=""
      name=""
      @change="selectTouched"
      class="combo-input-container__combobox"
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
  data() {
    return {
      isTouched: false,
    }
  },
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
}
</script>

<style lang="scss" scoped></style>
