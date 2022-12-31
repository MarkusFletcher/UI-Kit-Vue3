<script setup>
const emits = defineEmits(['change'])

const props = defineProps({
  name: {
    type: String,
    default: ''
  },
  id: {
    type: String,
    default: ''
  },
  value: {
    type: String,
    default: ''
  },
  checked: {
    type: Boolean,
    default: false
  },
  disabled: {
    type: Boolean,
    default: false
  },
  required: {
    type: Boolean,
    default: false
  },
})

const handleClick = (e) => {
  emits('change', e)
  // console.log(e)
}
</script>

<template>
  <input
    class="checkbox"
    type="checkbox"
    :id="id"
    :value="value"
    :checked="checked"
    :disabled="disabled"
    :required="required"
    @input="handleClick"
    >
    <!-- @input="handleClick($event)" -->
  <label :for="id">
    <slot></slot>
  </label>
</template>

<style lang="scss">
  .checkbox {
    position: absolute; // take it out of document flow
    opacity: 0; // hide it

    & + label {
      position: relative;
      cursor: pointer;
      padding: 0;
    }

    // Box.
    & + label:before {
      content: '';
      margin-right: 10px;
      display: inline-block;
      vertical-align: text-top;
      width: 20px;
      height: 20px;
      background-color: white;
      border: 2px solid var(--color-primary);
      transition: background-color .2s;
    }

    // Box hover
    &:hover + label:before {
      background-color: var(--color-primary);
    }
    
    // Box focus
    &:focus + label:before {
      background-color: var(--color-primary);
    }

    // Box checked
    &:checked + label:before {
      background-color: var(--color-primary);
    }
    
    // Disabled state label.
    &:disabled + label {
      color: #b8b8b8;
      cursor: auto;
    }

    // Disabled box.
    &:disabled + label:before {
      background-color: #ddd;
      border: 2px solid #ddd;
    }

    // Checkmark. Could be replaced with an image
    &:checked + label:after {
      content: '';
      position: absolute;
      left: 5px;
      top: 9px;
      background-color: white;
      width: 2px;
      height: 2px;
      box-shadow: 
        2px 0 0 white,
        4px 0 0 white,
        4px -2px 0 white,
        4px -4px 0 white,
        4px -6px 0 white,
        4px -8px 0 white;
      transform: rotate(45deg);
    }
  }
</style>