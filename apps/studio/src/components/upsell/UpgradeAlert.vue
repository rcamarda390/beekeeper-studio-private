<template>
  <div class="alert upgrade-alert">
    <i class="material-icons">info_outline</i>
    <div class="alert-body">{{ featureName }} needs a paid license</div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  props: {
    // Name of the feature that needs a license, e.g. "Oracle".
    featureName: {
      type: String,
      required: true,
    },
  },
});
</script>

<style lang="scss" scoped>
.alert.upgrade-alert {
  align-items: center;
}
</style>
