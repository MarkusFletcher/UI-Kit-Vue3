<script setup>
import {ref} from 'vue'

const props = defineProps({
  color: {
    type: String,
    required: false,
    default: 'default'
  },
  outline: {
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
  <button :class="['btn', {btn_rounded: rounded}, {btn_outline: outline}, `btn_${color}`]">
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

    margin-right: 20px;

    &:enabled:hover,
    &:enabled:focus {
      background-color: var(--color-primary-hover);
      border-color: var(--color-primary-hover);
    }

    &_second {
      background-color: var(--color-second);
      border-color: var(--color-second);

      &:enabled:hover,
      &:enabled:focus {
        background-color: var(--color-second-hover);
        border-color: var(--color-second-hover);
      }
    }

    &_rounded {
      border-radius: calc($height / 2);
    }

    &_outline {
      background-color: transparent;
      color: #333;

      &:enabled:hover,
      &:enabled:focus {
        color: #fff;
      }
    }

  }
</style>