<template>
  <section>
    <div class="container">
      <div class="row justify-content-center align-items-center">
        <div class="col-md-12 mt-3">
          <b-breadcrumb :items="items"></b-breadcrumb>
        </div>
      </div>
      <div class="row">
        <div class="col-md-12">
          <b-card no-body>
            <b-tabs card>
              <b-tab title="Password" >
                <changepassword/>
              </b-tab>
              <b-tab title="Signature" active>
                 <signature/>
              </b-tab>              
            </b-tabs>
          </b-card>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
  import changepassword from '@@/components/Setting/changepassword'
  import signature from '@@/components/Setting/changesignature'
  export default {
    layout: 'home',
      components: {
          changepassword,
         signature
        },
    data() {
      return {
        items: [{
            text: 'Setting',
            href: '/History'
          },
        ],

      }
    },
    methods: {
    
    },
  }

</script>
