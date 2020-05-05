<template >
  <section class="mb-5" style=""   >
    <Navbar />
    <nuxt class="p-3"   />
  </section>
</template>
<script>
import Vue from 'vue'
import { BootstrapVue, BootstrapVueIcons } from 'bootstrap-vue'

Vue.use(BootstrapVue)
Vue.use(BootstrapVueIcons)
import VueDocPreview from 'vue-doc-preview'
import VueSweetalert2 from 'vue-sweetalert2';
Vue.use(VueSweetalert2);
import Navbar from '@@/components/Navbar'
export default {
  components: {
        Navbar,
       
    },
  
}
</script>

<style>
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

</style>