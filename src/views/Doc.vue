<template>
  <div>
    <Topnav/>
    <div class="topNav">
      <div class="logo"></div>
      <div class="menu"></div>
    </div>
    <div class="content">
      <aside>
        <h2>Component List</h2>
        <ol>
          <li>
            <router-link to="/doc/switch">Switch</router-link>
          </li>
          <li>
            <router-link to="/doc/button">Button</router-link>
          </li>
          <li>
            <router-link to="/doc/dialog">Dialog</router-link>
          </li>
          <li>
            <router-link to="/doc/tabs">Tabs</router-link>
          </li>
        </ol>
      </aside>
      <main>main</main>

    </div>

  </div>
</template>

<script lang="ts">
  import Topnav from '../components/Topnav.vue';

  export default {
    components: {Topnav}
  };
</script>

<style lang="scss" scoped>
  aside {
    background: lightblue;
    width: 150px;
    padding: 16px;
    position: fixed;
    top: 0;
    left: 0;
    > h2 {
      margin-bottom: 4px;
    }
    > ol {
      > li {
        padding: 4px 0;
      }
    }
  }
</style>