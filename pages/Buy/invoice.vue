<template>
  <section>
    <div class="container">
      <div class="row justify-content-center align-items-center">
        <div class="col-md-12 mt-3">
          <b-breadcrumb :items="items"></b-breadcrumb>
        </div>
      </div>
      <div class="row mt-3 ">
        <div class="col-md-6">
          <h5>Invoice</h5>
          <hr>
        </div>
      </div>
     
      <div class="row">
        <div class="col-md-12">         
          <invoice/>
          
        </div>
      </div>
    </div>
  </section>
</template>
<script>
  import invoice from '@@/components/UpgradeAkun/Invoice'
  import NumberInputSpinner from 'vue-number-input-spinner'
  export default {
    layout: 'home',
    components: {
      NumberInputSpinner,
      invoice
    },
    data: function () {
      return {
        test: 10,
      };
    },
    data() {
      return {
        items: [{
            text: 'Buy',
            href: '#'
          },
          {
            text: 'Pembelian Produk',
            href: '#'
          },
          {
            text: 'Invoice',
            href: '#'
          },

        ]
      }
    }
  }

</script>
<style scoped>
  .middle {
    position: absolute;
    top: 30%;
  }
 

</style>
