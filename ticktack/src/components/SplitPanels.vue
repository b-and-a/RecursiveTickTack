<template>
  <div v-if="(config.panels === null) || (config.panels.length === 0)"
    style="height:100%; width:100%">
    <iframe v-bind:src="config.url" />
  </div>
  <splitpanes v-else-if="(config.direction === 'horizontal')"
    class="default-theme"
    style="height:100%; width:100%"
    horizontal>
    <span v-for="p in config.panels" :key="p.id">
      <split-panels :config="p" />
    </span>
  </splitpanes>
  <splitpanes v-else-if="(config.direction === 'vertical')"
    class="default-theme"
    style="height:100%; width:100%"
    vertical>
    <span v-for="p in config.panels" :key="p.id">
      <split-panels :config="p" />
    </span>
  </splitpanes>
  <div v-else></div>
</template>

<script>
import SplitPanels from './SplitPanels.vue'
import Splitpanes from 'splitpanes'
import 'splitpanes/dist/splitpanes.css'

export default {
  name: 'SplitPanels',
  components: {
    SplitPanels,
    Splitpanes
  },
  props: {
    config: {
      type: Object,
      required: true
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
