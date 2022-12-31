<script setup>
import {ref} from 'vue'

const props = defineProps({
  color: {
    type: String,
    required: false,
    default: 'default'
  },
  outlined: {
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
  <button :class="['btn', {btn_rounded: rounded}, {btn_outlined: outlined}, `btn_${color}`]">
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

    &_success {
      background-color: var(--color-success);
      border-color: var(--color-success);

      &:enabled:hover,
      &:enabled:focus {
        background-color: var(--color-success-hover);
        border-color: var(--color-success-hover);
      }
    }

    &_info {
      background-color: var(--color-info);
      border-color: var(--color-info);

      &:enabled:hover,
      &:enabled:focus {
        background-color: var(--color-info-hover);
        border-color: var(--color-info-hover);
      }
    }

    &_warning {
      background-color: var(--color-warning);
      border-color: var(--color-warning);

      &:enabled:hover,
      &:enabled:focus {
        background-color: var(--color-warning-hover);
        border-color: var(--color-warning-hover);
      }
    }

    &_danger {
      background-color: var(--color-danger);
      border-color: var(--color-danger);

      &:enabled:hover,
      &:enabled:focus {
        background-color: var(--color-danger-hover);
        border-color: var(--color-danger-hover);
      }
    }

    &_rounded {
      border-radius: calc($height / 2);
    }

    &_outlined {
      background-color: transparent;
      color: #333;

      &:enabled:hover,
      &:enabled:focus {
        color: #fff;
      }
    }

  }
</style>