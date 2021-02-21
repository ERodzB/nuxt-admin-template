<template>
  <div class="toast-container">
    <div :class="toastAccent"></div>
    <awesome-icon
      v-if="toastType === 'info'"
      name="info-circle"
      scale="3.5"
      class="toast-container__toast-logo color-yellow-300"
    />
    <awesome-icon
      v-else-if="toastType === 'success'"
      name="check-circle"
      scale="3.5"
      class="toast-container__toast-logo color-green-300"
    />
    <awesome-icon
      v-else
      name="exclamation-circle"
      scale="3.5"
      class="toast-container__toast-logo color-red-300"
    />
    <div class="toast-container__toast-message">
      <p v-if="toastType === 'info'" class="color-grey-200">Info</p>
      <p v-else-if="toastType === 'success'" class="color-grey-200">Success</p>
      <p v-else class="color-grey-200">Error</p>
      <span class="color-grey-400">{{ toastMessage }}</span>
    </div>
    <awesome-icon name="times" class="toast-container__close-logo" />
  </div>
</template>

<script>
export default {
  props: {
    toastType: {
      type: String,
      default: 'info',
    },
    toastMessage: {
      type: String,
      default: 'I am a message',
    },
  },
  computed: {
    toastAccent() {
      let toastAccentClass = 'toast-container__toast-accent--'
      if (this.toastType === 'error') return (toastAccentClass += 'error')
      if (this.toastType === 'success') return (toastAccentClass += 'success')
      return (toastAccentClass += 'info')
    },
  },
}
</script>

<style lang="scss" scoped></style>
