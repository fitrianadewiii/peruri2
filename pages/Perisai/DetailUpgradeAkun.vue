<template>
  <section style="">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <div class="container">
      <div class="row justify-content-center align-items-center ">
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
    layout:'home',
    name: 'demo',
    components: {
      KYC,
      Signature,
      Complete
    },
    data() {
      return {
        steps: [{
            label: 'KYC',
            slot: 'page1',
          },
          {
            label: 'Signature',
            slot: 'page2',
          },
          {
            label: 'Complete',
            slot: 'page3',
          },
        ],
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
      }
    },
  };

</script>
