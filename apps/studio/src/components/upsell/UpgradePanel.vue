<template>
  <div
    class="upgrade-panel vue-dialog"
    :class="{ 'upgrade-panel--standalone': standalone }"
  >
    <div class="dialog-content">
      <h3 class="dialog-c-title">
        {{ headingText }}
      </h3>
      <p class="dialog-c-subtitle">
        Not included in the Community Edition.
      </p>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  props: {
    // Name of the feature the user just tried to use, e.g. "Backup & Restore".
    featureName: {
      type: String,
      default: null
    },
    // When true, the panel adds its own card chrome (surface, radius, shadow)
    // for inline placement. When false it's bare, so a modal supplies chrome.
    standalone: {
      type: Boolean,
      default: false
    }
  },
  computed: {
    headingText(): string {
      if (this.featureName) return `${this.featureName} needs a paid license`
      return 'This feature needs a paid license'
    }
  }
})
</script>
