<script setup>
import {ref} from 'vue'

const props = defineProps({
  color: {
    type: String,
    required: false
  },
  rounded: {
    type: String,
    required: false
  }
})
</script>

<template>
  <button :class="['btn', {btn_rounded: rounded}]">
    <slot></slot>
  </button>
</template>

<style lang="scss" scoped>
  .btn {
    $height: 36px;

    font-size: 16px;
    color: #fff;
    cursor: pointer;
    height: $height;
    padding-left: 20px;
    padding-right: 20px;
    background-color: var(--color-primary);
    border: 2px solid var(--color-primary);
    transition: .2s;

    &_rounded {
      border-radius: calc($height / 2);
    }

    &_outline {
      background-color: transparrent;
    }

    &:enabled:hover,
    &:enabled:focus {
      background-color: var(--color-primary-hover);
      border-color: var(--color-primary-hover);
    }
  }
</style>