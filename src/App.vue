<script setup>
import { ref } from 'vue'
import VHeader from '@/components/layout/Header.vue'
import VSidebar from '@/components/layout/Sidebar.vue'

const isOpenMenu = ref(false)

const toggleMenu = () => {
  isOpenMenu.value = !isOpenMenu.value
}
</script>

<template>
  <div class="wrapper">
    <v-header @togglemenu="toggleMenu"></v-header>
    <main class="main">
      <v-sidebar :isOpen="isOpenMenu"></v-sidebar>
      <div class="content" :class="{content_full: !isOpenMenu}">
        <router-view></router-view>
      </div>
    </main>
  </div>
</template>

<style lang="scss">
  .main {
  }
  .content {
    margin-left: 250px;
    padding: 40px 20px;
    transition: margin .2s;
    &_full {
      margin-left: 0px;
    }
  }
  // @import './styles/style.scss';
</style>
