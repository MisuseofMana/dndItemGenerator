<template>
  <div id="app">
    <site-header/>
    <item-generator/>
  </div>
</template>

<script>
import SiteHeader from './components/SiteHeader'
import ItemGenerator from './components/ItemGenerator'
import './assets/styles/global.css';

export default {
  name: 'App',
  components: {
    SiteHeader,
    ItemGenerator,
  }
}

</script>

<style>

</style>


