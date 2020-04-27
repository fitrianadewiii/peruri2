<template>
  <section style="">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <div class="container">
      <div class="row justify-content-center align-items-center" style="height:100vh;">
        <div class="col-md-12">
          <vue-good-wizard :steps="steps" :onNext="nextClicked" :onBack="backClicked">
            <div slot="page1">
               <FormRegister />
            </div>
            <div slot="page2">
              <Aktivasi />
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
  import FormRegister from '@@/components/Register/FormRegister'
  import Aktivasi from '@@/components/Register/Aktivasi'
  import Complete from '@@/components/Register/Complete'

  Vue.use(VueGoodWizard);
  export default {
    layout:'register',
    name: 'demo',
    components: {
      FormRegister,
      Aktivasi,
      Complete
    },
    data() {
      return {
        steps: [{
            label: 'Register',
            slot: 'page1',
          },
          {
            label: 'Aktivasi',
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
      nextClicked(currentPage) {
        console.log('next clicked', currentPage)
        return true; //return false if you want to prevent moving to next page
      },
      backClicked(currentPage) {
        console.log('back clicked', currentPage);
        return true; //return false if you want to prevent moving to previous page
      }
    },
  };

</script>
