<template>
  <div>
    <div class="tabs">
      <div v-for="(route, index) in visitedRoute" class="tab-item" :key="index" :class="{active: route.path === $route.path}">
        <router-link :to="route.path">{{route.title}}</router-link> <span @click="closeRoute" :data-path="route.path" class="close-icon">x</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Tabs",
  data() {
    return {
      visitedRoute: []
    }
  },
  watch: {
    $route: function () {
      if (this.visitedRoute.some(i => i.path === this.$route.path)) {
        return;
      }
      this.visitedRoute.push({
        ...this.$route,
        title: this.$route.meta.title || '未命名'
      });
    }
  },
  methods: {
    closeRoute(e) {
      if (this.visitedRoute.length < 2) {
        return;
      }
      let targetIndex = this.visitedRoute.findIndex(item => item.path === e.target.dataset.path);
      if (targetIndex !== -1) {
        this.visitedRoute.splice(targetIndex, 1);
      }
    }
  }
};
</script>

<style scoped>
  .tabs {
    display: flex;
  }

  .tab-item {
    margin: 10px;
    padding: 10px;
    border: 1px solid #42b983;
  }

  .tab-item.active {
    background: #42b983;
    color: #fff;
  }

  .close-icon {
    cursor: pointer;
  }
</style>
