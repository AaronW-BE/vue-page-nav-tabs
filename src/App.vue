<template>
  <div id="app">
    <Tabs />
    <keep-alive>
      <router-view />
    </keep-alive>
  </div>
</template>

<script>
  import Tabs from "./components/Tabs";
  export default {
    components: {Tabs},
    data() {
      return {
      };
    },
    methods: {}
  }
</script>
<style>

</style>
