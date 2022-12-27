<script setup>
import VButton from '@/components/ui/Button.vue'
</script>

<template>
  <h1 class="heading-1">Button</h1>
  <div class="row">
    <v-button>Button</v-button>
  </div>
  <div class="row">
    <v-button :rounded="true">Button</v-button>
  </div>
</template>

<style lang="scss" scoped>
  .row {
    margin-bottom: 20px;
  }
</style>