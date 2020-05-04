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
                  <div class="row">
                    <div class="col-md-12 text-right">
                      <button class="btn btn-info">Add Document</button>
                      <hr>
                    </div>
                  </div>
                  <div class="row">
                    <div class="col-3">
                      <div class="card card-block">
                        <div class="card-body text-center">
                          <img src="/img/179483.PNG" alt="">
                          <p><b>Doc1.pdf</b></p>
                        </div>
                      </div>
                    </div>
                  </div>
                  <div class="row">
                    <div class="col-md-12">
                      <hr>
                      <VueDocPreview value="newteach.pbworks.com%2Ff%2Fele%2Bnewsletter.docx" type="office" />
                    </div>
                  </div>
                </div>
                <div class="col-md-4" style="margin-top:auto">
                  <b-form-checkbox id="checkbox-1" v-model="status" name="checkbox-1" value="accepted"
                    unchecked-value="not_accepted">
                    Save to Digital Locker
                  </b-form-checkbox>
                  <b-form-checkbox id="checkbox-1" v-model="status" name="checkbox-1" value="accepted"
                    unchecked-value="not_accepted">
                    I accept the terms and condition
                  </b-form-checkbox>

                  <div class="row">
                    <div class="col-md-12">
                      <button v-b-modal.modal-1 class="btn btn-success btn-block">Bubuhkan</button>
                    </div>
                  </div>

                </div>
              </div>
            </div>
          </div>
        </div>
      </div>


      <b-modal v-if="modal" id="modal-1" size="sm" hide-footer="true" title="Verification Code">
        <div class="row">
          <div class="col-md-12 text-center">
            <p>I approve this document</p>
          </div>
        </div>
        <div class="row">
          <div class="col-md-12">
            <b-form-input v-model="text" placeholder="Enter your otp code"></b-form-input>
          </div>
        </div>
        <div class="row mt-2">
          <div class="col-md-12 text-center">
            <button @click="showAlert" class="btn btn-success btn-block">Verify</button>
          </div>
        </div>
        <div class="row mt-3 mb-2">
          <div class="col-md-12 text-center">
            <small> Verification code has been sent to ******75651 and ****ds@gmail.com </small>
          </div>
        </div>
      </b-modal>
    </div>
  </section>
</template>
<script>
  import VueDocPreview from 'vue-doc-preview'
  // main.js
  import Vue from 'vue';
  import VueSweetalert2 from 'vue-sweetalert2';

  // If you don't need the styles, do not connect
  // import 'sweetalert2/dist/sweetalert2.min.css';

  Vue.use(VueSweetalert2);
  export default {

    layout: 'home',
    components: {
      VueDocPreview,
    },
    data() {
      return {
        modal: true,
        items: [{
            text: 'Peruri Tera',
            href: '/PeruriTera'
          },
          {
            text: 'Upload Dokumen',
            href: '/PeruriTera/UploadDocument'
          },

        ]
      }
    },
    methods: {
      showAlert() {
        // Use sweetalert2
        this.$swal('SUCCESS', 'Please Check Your History', 'success');
        this.modal = false;
        this.$router.push({
          path: `/Perisai/History`,
        })
      },
    },
  }

</script>
<style>

</style>
