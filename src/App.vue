<template>
  <div id="app">
    <site-header @change-page="togglePage($event)"/>
    <char-generator v-if="page==='char'"/>
    <item-generator v-else-if="page==='item'"/>
    <readout-block/>
  </div>
</template>

<script>
import SiteHeader from './components/SiteHeader'
import ItemGenerator from './components/ItemGenerator'
import CharGenerator from './components/CharGenerator'
import ReadoutBlock from './components/ReadoutBlock'

import './assets/styles/global.css';

export default {
  name: 'App',
  data() {
    return {
      page: 'item',
    }
  },
  methods: {
    togglePage(newPage) {
      this.page = newPage
    }
  },
  components: {
    SiteHeader,
    ItemGenerator,
    CharGenerator,
    ReadoutBlock,
  }
}

</script>

<style>

</style>


