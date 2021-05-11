<template>
  <div id="app">
    <ToSend />
  </div>
</template>

<script>
import ToSend from './components/ToSend.vue';
import "tailwindcss/tailwind.css"

export default {
  name: 'App',
  components: {
    ToSend
  }
}
</script>

<style>
</style>