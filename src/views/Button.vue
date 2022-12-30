<script setup>
import VButton from '@/components/ui/Button.vue'

const clickOnButton = () => {
  alert('You clicked button')
}
</script>

<template>
  <h1 class="heading-1">Button</h1>
  <h2 class="heading-2">Colors</h2>
  <div class="row">
    <v-button>Button</v-button>
    <v-button color="second">Button</v-button>
    <v-button color="success">Button</v-button>
    <v-button color="info">Button</v-button>
    <v-button color="warning">Button</v-button>
    <v-button color="danger">Button</v-button>
  </div>
  <h2 class="heading-2">Rounded</h2>
  <div class="row">
    <v-button rounded="true">Button</v-button>
    <v-button color="second" rounded="true">Button</v-button>
    <v-button color="success" rounded="true">Button</v-button>
    <v-button color="info" rounded="true">Button</v-button>
    <v-button color="warning" rounded="true">Button</v-button>
    <v-button color="danger" rounded="true">Button</v-button>
  </div>
  <h2 class="heading-2">Outlined</h2>
  <div class="row">
    <v-button outlined="true">Button</v-button>
    <v-button color="second" outlined="true">Button</v-button>
    <v-button color="success" outlined="true">Button</v-button>
    <v-button color="info" outlined="true">Button</v-button>
    <v-button color="warning" outlined="true">Button</v-button>
    <v-button color="danger" outlined="true">Button</v-button>
  </div>
  <h2 class="heading-2">Rounded & outlined</h2>
  <div class="row">
    <v-button outlined="true" rounded="true">Button</v-button>
    <v-button color="second" outlined="true" rounded="true">Button</v-button>
    <v-button color="success" outlined="true" rounded="true">Button</v-button>
    <v-button color="info" outlined="true" rounded="true">Button</v-button>
    <v-button color="warning" outlined="true" rounded="true">Button</v-button>
    <v-button color="danger" outlined="true" rounded="true">Button</v-button>
  </div>
  <h2 class="heading-2">Event</h2>
  <div class="row">
    <v-button @click="clickOnButton" color="danger">@click</v-button>
  </div>
</template>

<style lang="scss" scoped>
  .row {
    margin-bottom: 20px;
  }
</style>