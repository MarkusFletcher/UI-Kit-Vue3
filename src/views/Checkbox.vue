<script setup>
import {ref} from 'vue'
import VCheckbox from '@/components/ui/checkbox/Checkbox.vue'

const isChecked = ref(true)


</script>

<template>
  <h1 class="heading-1">Checkbox</h1>
  {{ isChecked }}
  <div class="row">
    <v-checkbox
      name="checkbox-1"
      id="checkbox-1"
      value="checkbox-1"
      v-model:checked="isChecked">
      Checkbox
    </v-checkbox>
  </div>
  <div class="row">
    <v-checkbox
      name="checkbox-2"
      id="checkbox-2"
      value="checkbox-2"
      v-model:checked="isChecked">
      Checkbox
    </v-checkbox>
  </div>
  
</template>