<template>
  <div class="layout">
    <Topnav class="nav"/>
    <div class="content">
      <aside v-if="asideVisible">
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
      <main>
        <router-view/>
      </main>
    </div>
  </div>
</template>

<script lang="ts">
  import Topnav from '../components/Topnav.vue';
  import {inject, Ref} from 'vue';

  export default {
    components: {Topnav},
    setup() {
      const asideVisible = inject<Ref<boolean>>('asideVisible');
      console.log(asideVisible.value);
      return {asideVisible};
    }
  };
</script>

<style lang="scss" scoped>
  .layout {
    display: flex;
    flex-direction: column;
    height: 100vh;
    > .nav {
      flex-shrink: 0;
    }
    > .content {
      flex-grow: 1;
      padding-top: 60px;
      padding-left: 156px;
      @media (max-width: 500px) {
        padding-left: 0;
      }
    }
  }
  .content {
    display: flex;
    > aside {
      flex-shrink: 0;
    }
    > main {
      flex-grow: 1;
      padding: 16px;
      background: lightgreen;
    }

  }
  aside {
    background: lightblue;
    width: 160px;
    position: fixed;
    top: 0;
    left: 0;
    padding: 100px 16px 16px;
    height: 100%;
    > h2 {
      margin-bottom: 4px;
    }
    > ol {
      > li {
        padding: 4px 0;
      }
    }
    @media (max-width: 500px) {
      position: fixed;
      top: 0;
      left: 0;
      padding-top: 70px;
    }
  }
  main {
    overflow: auto;
  }
</style>