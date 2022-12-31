<script setup>
import {ref} from 'vue'

const props = defineProps({
  isOpen: {
    type: Boolean,
    required: true
  }
})

const links = ref([
  {
    name: 'Typegraphy',
    href: '/typography'
  },
  {
    name: 'Button',
    href: '/button'
  },
  {
    name: 'Checkbox',
    href: '/checkbox'
  }
])
</script>

<template>
  <aside :class="['sidebar',{sidebar_isopen: isOpen}]">
    <router-link class="sidebar__link" active-class="sidebar__link_active" v-for="link in links" :key="link.name" :to="link.href">
      {{ link.name }}
    </router-link>
  </aside>
</template>

<style lang="scss" scoped>
  .sidebar {
    left: 0;
    top: 62px;
    position: fixed;
    background-color: #fff;
    width: 250px;
    height: 100%;
    transition: .2s;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.07);
    transform: translateX(-250px);
    &_isopen {
      transform: translateX(0);
    }
    &__link {
      display: block;
      padding: 12px 24px;
      transition: .2s;
      &:hover {
        background-color: var(--color-primary);
        color: #fff;
      }
      &_active {
        background-color: var(--color-primary);
        color: #fff;
      }
    }
  }
</style>