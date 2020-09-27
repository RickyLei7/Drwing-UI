<template>
  <div class="topNav">
    <div class="logo"><img src="../imgs/LOGO.png" alt="LOGO"></div>
    <ul class="menu">
      <li>menu1</li>
      <li>menu2</li>
    </ul>
    <span class="toggleAside" @click="toggleMenu"></span>
  </div>
</template>

<script lang="ts">
  import {inject, Ref} from 'vue';

  export default {
    setup() {
      const asideVisible = inject<Ref<boolean>>('asideVisible');
      console.log(asideVisible.value);
      const toggleMenu = () => {
        asideVisible.value = !asideVisible.value;
      };
      return {toggleMenu};
    }

  };
</script>

<style lang="scss" scoped>
  .topNav {
    border: 1px solid red;
    background: pink;
    display: flex;
    padding: 16px;
    position: relative;
    z-index: 10;
    justify-content: center;
    align-items: center;
    > .logo {
      border: 1px solid blue;
      max-width: 6em;
      margin-right: auto;
      > img {
        border: 1px solid red;
        max-width: 48px;
      }
    }
    > .menu {
      display: flex;
      white-space: nowrap;
      flex-wrap: nowrap;
      > li {
        margin: 0 1em;
      }
    }
    > .toggleAside{
      border: 10px solid red;
      width: 24px;
      height: 24px;
      background: red;
      position: absolute;
      left: 16px;
      top: 50%;
      transform: translateY(-50%);
      display: none;

    }
    @media (max-width: 500px) {
      > .menu {display: none;}
      > .logo {margin: 0 auto;}
      > .toggleAside{display: inline-block;}
    }
  }
</style>