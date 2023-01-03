<script setup>
import {ref} from 'vue'
import VCheckbox from '@/components/ui/checkbox/Checkbox.vue'
import VCheckboxGroup from '@/components/ui/checkbox/CheckboxGroup.vue'

const isChecked1 = ref(false)
const isChecked2 = ref(false)
const isDisabled2 = ref(true)

const listOfHeroes = ref([
  {
    id: 'hero_1',
    name: 'Iron Man'
  },
  {
    id: 'hero_2',
    name: 'Spider Man'
  },
  {
    id: 'hero_3',
    name: 'Venom'
  },
  {
    id: 'hero_4',
    name: 'Dr. Strange'
  },
])

const selectedHeroes = ref(['hero_2'])

const updateSelectedHeroes = ({id, checked}) => {
  if(checked) {
    selectedHeroes.value.push(id)
  } else {
    selectedHeroes.value.splice(selectedHeroes.value.indexOf(id), 1)
  }
}

const checkboxClick1 = (e) => {
  console.log(e)
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
  <h2 class="heading-2">Checkbox</h2>
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
  <h2 class="heading-2">Checkbox Group</h2>
  <div class="row row_block">
    {{ selectedHeroes }}
  </div>
  <div class="row">
    <v-checkbox-group
      name="heroes"
      :options="listOfHeroes"
      v-model:selected="selectedHeroes"
      @updateSelected="updateSelectedHeroes">
    </v-checkbox-group>
  </div>
  
</template>