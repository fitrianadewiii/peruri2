<template>
  <section style="">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <div class="container">
      <!-- <div class="row justify-content-center align-items-center ">
        <div class="col-md-12">
          <vue-good-wizard class="mb-5" :steps="steps" >
            <div slot="page1">
               <KYC />
            </div>
            <div slot="page2">
              <Signature />
            </div>
            <div slot="page3">
              <Complete />
            </div>            
          </vue-good-wizard>          
        </div>
      </div> -->
      <div class="row justify-content-center align-items-center">
        <div class="col-md-12 mt-3">
          <b-breadcrumb :items="items"></b-breadcrumb>
        </div>
      </div>
      <div class="row mt-3">
        <div class="col-md-12">
          <div class="card" v-if="kyc">
            <div class="card-body">
              <div class="row" >
                <div class="col-md-12">
                  <KYC />
                </div>
              </div>
              <div class="row">
                <div class="col-md-12 text-right">
                  <hr>
                  <button @click="buttonnext()" class="btn btn-info">Next</button>
                </div>
              </div>
            </div>
           
          </div>
           <div class="card" v-if="signature">
            <div class="card-body">
              <div class="row" >
                <div class="col-md-12">
                  <Signature />
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
  import Vue from 'vue';
  import VueGoodWizard from 'vue-good-wizard';
  import KYC from '@@/components/UpgradeAkun/KYC'
  import Signature from '@@/components/UpgradeAkun/Signature'
  import Complete from '@@/components/UpgradeAkun/Complete'

  Vue.use(VueGoodWizard);
  export default {
    layout: 'home',
    name: 'demo',
    components: {
      KYC,
      Signature,
      Complete
    },
    data() {
      return {
        kyc: true,
        signature: false,
        items: [{
          text: 'Perisai',
          href: '#'
        }],
        // steps: [{
        //     label: 'KYC',
        //     slot: 'page1',
        //   },
        //   {
        //     label: 'Signature',
        //     slot: 'page2',
        //   },
        //   {
        //     label: 'Complete',
        //     slot: 'page3',
        //   },
        // ],
      };
    },
    methods: {
      // nextClicked(currentPage) {
      //   console.log('next clicked', currentPage)
      //   return true; //return false if you want to prevent moving to next page
      // },
      backClicked(currentPage) {
        console.log('back clicked', currentPage);
        return true; //return false if you want to prevent moving to previous page
      },
      buttonnext() {
        this.kyc = false;
        this.signature = true;
      }
    },
  };

</script>
