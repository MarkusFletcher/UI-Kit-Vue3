<template>
  <header class="header">
      <button class="header__togle-menu-btn" @click="$emit('togglemenu')">
        <img src="@/assets/burger.svg" alt="">
      </button>
      <router-link to="/">UI KIT (Vue 3 + Composition API + Vite)</router-link>
  </header>
</template>

<style lang="scss" scoped>
  .header {
    background-color: #fff;
    font-weight: bold;
    padding: 0 20px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.07);
    height: 62px;
    display: flex;
    align-items: center;
    z-index: 1;
    position: relative;

    &__togle-menu-btn {
      background-color: transparent;
      border: none;
      cursor: pointer;
      margin-right: 30px;
      display: flex;
      align-items: center;
    }
  }
</style>