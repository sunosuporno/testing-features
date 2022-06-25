<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from '@/components/HelloWorld.vue'
</script>

<template>
  <RouterView />
</template>

<style>
@import '@/assets/base.css';
*{
  box-sizing: border-box;
  margin: 0;
}
body{
  width: 95%;
  margin: auto;
}
</style>
