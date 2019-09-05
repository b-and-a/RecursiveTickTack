<template>
  <split-panels :config="splitPanelsConfig3" />
</template>

<script>
import SplitPanels from './components/SplitPanels.vue'

export default {
  name: 'app',
  components: {
    SplitPanels
  },
  data() {
    return {
      splitPanelsConfig1: {
        direction: 'horizontal',
        panels: [{
          id: 'p00',
          url: 'a.html',
          panels: []
        }, {
          id: 'p01',
          url: 'b.html',
          panels: []
        }, {
          id: 'p02',
          url: 'c.html',
          panels: []
        }]
      },
      splitPanelsConfig2: {
        id: 'p00',
        url: 'a.html',
        panels: []
      },
      splitPanelsConfig3: {
        direction: 'horizontal',
        panels: [{
          id: 'p00',
          url: 'a.html',
          panels: []
        }, {
          id: 'p01x',
          direction: 'vertical',
          panels: [{
            id: 'p01-p00',
            url: 'a.html',
            panels: []
          }, {
            id: 'p01-p01',
            url: 'a.html',
            panels: []
          }, {
            id: 'p1-p02x',
            direction: 'horizontal',
            panels: [{
              id: 'p01-p02-p00',
              url: 'a.html',
              panels: []
            }, {
              id: 'p01-p02-p01',
              url: 'b.html',
              panels: []
            }]
          }]
        }, {
          id: 'p02',
          url: 'c.html',
          panels: []
        }]
      },
    };
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
