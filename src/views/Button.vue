<script setup>
import VButton from '@/components/ui/Button.vue'
</script>

<template>
  <h1 class="heading-1">Button</h1>
  <div class="row">
    <v-button>Button</v-button>
    <v-button :color="'second'">Button</v-button>
  </div>
  <div class="row">
    <v-button :rounded="true">Button</v-button>
    <v-button :color="'second'" :rounded="true">Button</v-button>
  </div>
  <div class="row">
    <v-button :outline="true">Button</v-button>
    <v-button :color="'second'" :outline="true">Button</v-button>
  </div>
  <div class="row">
    <v-button :outline="true" :rounded="true">Button</v-button>
    <v-button :color="'second'" :outline="true" :rounded="true">Button</v-button>
  </div>
</template>

<style lang="scss" scoped>
  .row {
    margin-bottom: 20px;
  }
</style>