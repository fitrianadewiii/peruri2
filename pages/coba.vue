<template>
  <div>
    <div id="app">
      <vuefinder url="vuefinder"></vuefinder>
    </div>
  </div>
</template>
<script>
 import Vue from 'vue';
    import vuefinder from 'vuefinder/src/Finder.vue';
  export default {
      name: 'App',
    components: {
      vuefinder,
      // FontAwesomeIcon
    },
  }

</script>
