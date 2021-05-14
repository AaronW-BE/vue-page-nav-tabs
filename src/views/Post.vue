<template>
  <div>
    <h1>Post detail</h1>
    <div>{{id}}</div>
  </div>
</template>

<script>
export default {
  name: "Post",
  props: {
    id: [Number, String]
  }
}
</script>

<style scoped>

</style>
