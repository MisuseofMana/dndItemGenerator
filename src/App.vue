<template>
  <div id="app">
    <!-- What does @ mean? @change-page = v-on:change-page - @ = v-on -->
    <!-- SiteHeader button click emits change page event and payload -->
    <!-- We run togglePage function and pass in the argument $event as the payload -->
    <site-header @change-page="togglePage($event)"/>
    <item-generator v-if="activePageIs==='item'"/>
  </div>
</template>

<script>
// import and declare our vue component
import SiteHeader from './components/SiteHeader'
import ItemGenerator from './components/ItemGenerator'

// importing stylesheet from assets
import './assets/styles/global.css';

//all vue components including root componene need a default export, in most cases
export default {
  name: 'App',
  data() {
    return {
      //default set page state to item.
      activePageIs: 'item',
      selectedBoxes:[],
    }
  },
  methods: {
    // Uses change-page payload to determine page state 
    togglePage(newPage) {
      this.page = newPage
    }
  },
  components: {
    // App file's references
    SiteHeader,
    ItemGenerator,
  }
}

</script>

<style>
</style>


