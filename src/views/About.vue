<template>
  <div class="about">
    <h1>This is an about page</h1>
    <router-link :to="{name: 'Home'}">Home</router-link>

    <div>
      <router-link :to="{name: 'Post', params: {id: 1}}">1</router-link>
    </div>
    <div>
      <router-link :to="{name: 'Post', params: {id: 2}}">2</router-link>
    </div>
    <div>
      <router-link :to="{name: 'Post', params: {id: 3}}">3</router-link>
    </div>
  </div>
</template>
