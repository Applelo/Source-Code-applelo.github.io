<template lang="pug">
  Error(:error="error")
</template>

<script lang="ts">
import Vue from 'vue';
export default Vue.extend({
  props: ['error'],
  layout: 'errors',
});
</script>
