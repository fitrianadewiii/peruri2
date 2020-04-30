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
          <h5>Pembelian Produk</h5>
          <hr>
          <div class="row ">
            <div class="col-md-4">
              <h6 class="middle">Perisai Rp.3000</h6>
            </div>
            <div class="col-md-8 text-center">
              <NumberInputSpinner style="width:40%;" :integerOnly="false" value='10' :max="1000" v-model="test" />
            </div>
          </div>
          <div class="row mt-2 ">
            <div class="col-md-4">
              <h6 class="middle">Tera Rp.6000</h6>
            </div>
            <div class="col-md-8">
              <NumberInputSpinner style="width:40%;" :integerOnly="false" value='10' :max="1000" v-model="test" />
            </div>
          </div>
          <div class="row mt-2 ">
            <div class="col-md-4">
              <h6 class="middle">Tera Rp.6000</h6>
            </div>
            <div class="col-md-8">
              <NumberInputSpinner style="width:40%;" :integerOnly="false" value='10' :max="1000" v-model="test" />
            </div>
          </div>
          <hr>
        </div>
      </div>
      <div class="row mt-2">
          <div class="col-md-6">
            <h5>Produk</h5>
          </div>
           <div class="col-md-6 text-right">
          <button @click="Chart()" class="btn btn-info">View Cart</button>
          </div>
      </div>
      <div class="row">
        <div class="col-md-12">         
          <hr>
          <div class="row ">
            <div class="col-md-12">
              <div class="scrolling-wrapper row flex-row flex-nowrap">
                <div class="col-3">
                  <div class="card card-block">
                    <div class="card-body">
                      <div class="row">
                        <div class="col-md-6 ">
                          <p><b>BEST DEAL</b></p>
                        </div>
                        <div class="col-md-6 text-right ">
                          <input type="checkbox" class="mr-3" />
                        </div>
                      </div>
                      <div class="row mt-1">
                        <div class="col-md-12">
                          <h5>30.000</h5>
                        </div>
                      </div>
                      <div class="row mt-1">
                        <div class="col-md-12">
                          <hr>
                        </div>
                      </div>
                      <div class="row mt-1">
                        <div class="col-md-12">
                          <p>10x Perisai RP.3000</p>
                          <p>20x Tera RP.3000</p>
                          <p>10x Tera RP.6000</p>
                          <p>10mb DigitalLocker</p>
                        </div>
                      </div>

                    </div>
                  </div>
                </div>
                <div class="col-3">
                  <div class="card card-block">
                      
                    <div class="card-body">
                     
                      <div class="row">                       
                        <div class="col-md-6 ">
                          <p><b>BEST DEAL</b></p>
                        </div>
                        <div class="col-md-6 text-right ">
                          <input type="checkbox" class="mr-3" />
                        </div>
                      </div>
                      <div class="row mt-1">
                        <div class="col-md-12">
                          <h5>30.000</h5>
                        </div>
                      </div>
                      <div class="row mt-1">
                        <div class="col-md-12">
                          <hr>
                        </div>
                      </div>
                      <div class="row mt-1">
                        <div class="col-md-12">
                          <p>10x Perisai RP.3000</p>
                          <p>20x Tera RP.3000</p>
                          <p>10x Tera RP.6000</p>
                          <p>10mb DigitalLocker</p>
                        </div>
                      </div>

                    </div>
                  </div>
                </div>
               
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
  import NumberInputSpinner from 'vue-number-input-spinner'
  export default {
    layout: 'home',
    components: {
      NumberInputSpinner,
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

        ]
      }
    },
     methods: {
      Chart() {
        this.$router.push({
          path: `/Buy/invoice`,
        })
      },
     }
  }

</script>
<style scoped>
  .middle {
    position: absolute;
    top: 30%;
  }
 

</style>
