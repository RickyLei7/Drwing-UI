<template>
  <div>
    <Topnav />
    <div class="topNav">
      <div class="logo"></div>
      <div class="menu"></div>
    </div>
    <div class="content">
      <aside>sideBar</aside>
      <main>main</main>

    </div>

  </div>
</template>

<script lang="ts">
  import Topnav from '../components/Topnav.vue'

  export default {
    components:{Topnav}
  }
</script>