<script setup>
import {ref} from 'vue'
import VCheckbox from '@/components/ui/checkbox/Checkbox.vue'

const isChecked1 = ref(false)
const isChecked2 = ref(false)
const isDisabled2 = ref(true)

const checkboxClick1 = () => {
  isChecked1.value = !isChecked1.value
  changeActivity2()
}

const checkboxClick2 = () => {
  isChecked2.value = !isChecked2.value
}

const changeActivity2 = () => {
  isDisabled2.value = !isDisabled2.value
}
</script>

<template>
  <h1 class="heading-1">Checkbox</h1>
  <div class="row">
    <v-checkbox
      name="checkbox-1"
      id="checkbox-1"
      value="checkbox-1"
      :checked="isChecked1"
      @change="checkboxClick1">
      Checkbox. isChecked:{{ isChecked1 }}
    </v-checkbox>
  </div>
  <div class="row">
    <v-checkbox
      name="checkbox-2"
      id="checkbox-2"
      value="checkbox-2"
      :disabled="isDisabled2"
      :checked="isChecked2"
      @change="checkboxClick2">
      Checkbox. disabled: {{ isDisabled2 }} isChecked:{{ isChecked2 }}
    </v-checkbox>
  </div>
  
</template>