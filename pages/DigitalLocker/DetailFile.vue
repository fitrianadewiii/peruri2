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
          <div class="card">
            <div class="card-body">
              <div class="row  ">
                <div class="col-md-8">
                  <div class="row" style="height:100vh">
                    <div class="col-md-12">
                      <hr>
                      <VueDocPreview value="newteach.pbworks.com%2Ff%2Fele%2Bnewsletter.docx" type="office"  />
                    </div>
                  </div>
                </div>
                <div class="col-md-4">
                  <div class="row">
                    <div class="col-md-12 ">
                     <detail/>
                    </div>
                  </div>
                  <div class="row mt-2" >
                    <div class="col-md-12 ">
                     <history/>
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
  import VueDocPreview from 'vue-doc-preview'
  import detail from '@@/components/DetailDocument'
  import history from '@@/components/History'
  export default {

    layout: 'home',
    components: {
     VueDocPreview,
      detail,
      history
    },
    data() {
      return {
        modal: true,
        items: [{
           
            text: 'Nama Folder',
            href: ''
          },
          {
           
            text: 'Nama File',
            href: ''
          },

        ]
      }
    },
    methods: {
      showAlert() {
        // Use sweetalert2
        this.$swal('SAVED','Your Document will be saved on Digital Locker', 'success');
        this.modal = false;
      },
    },
  }

</script>
<style>

</style>
