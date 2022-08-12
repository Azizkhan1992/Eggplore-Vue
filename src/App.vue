<template>
  <div id="app">
    <eggplore-layout></eggplore-layout>
  </div>
</template>

<script>
import '@/assets/styles/eggplore-header.css'
import '@/assets/styles/eggplore-content-one.css'
import '@/assets/styles/eggplore-content-two.css'
import '@/assets/styles/eggplore-content-three.css'

import EggploreLayout from './components/EggploreLayout.vue'
export default {
  name: 'App',
  components: {
    EggploreLayout
  }
}
</script>

<style>

</style>
