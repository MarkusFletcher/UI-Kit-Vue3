<script setup>
import VCheckbox from '@/components/ui/checkbox/Checkbox.vue'

const emits = defineEmits(['updateSelected'])

const props = defineProps({
  name: {
    type: String,
    required: true
  },
  options: {
    type: Array,
    required: true,
    validator: (value) => {
      const hasNameKey = value.every(item => Object.keys(item).includes('name'))
      const hasIdKey = value.every(item => Object.keys(item).includes('id'))
      return hasNameKey && hasIdKey
    }
  },
  selected: {
    type: Array,
    default: []
  }
})

const updateSelected = ({target}) => {
  emits('updateSelected', { id: target.id, checked: target.checked })
}
</script>

<template>
  <div class="checkbox-group">
    <v-checkbox 
      class="chexkbox-group__item"
      v-for="option in options"
      :key="option.id"
      :id="option.id"
      :name="name"
      :checked="selected.includes(option.id)"
      @change="updateSelected">
      {{ option.name }}
    </v-checkbox>
  </div>
</template>

<style lang="scss" scoped>
  .chexkbox-group {
    &__item {
      margin-bottom: 16px;
    }
  }
</style>