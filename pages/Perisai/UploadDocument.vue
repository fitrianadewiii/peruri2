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
                  <div class="row">
                    <div class="col-md-12">
                      <hr>
                      <b-form-group id="input-group-1" label="Location:" label-for="input-1"
                        description="Input Your Location">
                        <b-form-input id="input-1" type="text" required placeholder="Input Your Location">
                        </b-form-input>
                      </b-form-group>
                      <b-form-group id="input-group-1" label="Comment:" label-for="input-1"
                        description="Input Your Comment">
                        <b-form-input id="input-1" type="text" required placeholder="Input Your Comment">
                        </b-form-input>
                      </b-form-group>
                    </div>
                  </div>
                </div>
                <div class="col-md-4">
                  <div class="row mt-5">
                    <div class="col-md-12 mt-3">
                      <button class="btn btn-primary btn-block">Add Signature</button>
                      <button class="btn btn-info btn-block">Set Position</button>
                      <button class="btn btn-secondary btn-block">Cancel</button>
                      <div @click="showAlert" class="mt-2">
                      <b-form-checkbox  id="checkbox-1"  name="checkbox-1" value="accepted"
                        unchecked-value="not_accepted" >
                        Save to My Digital Locker
                      </b-form-checkbox>
                      </div>
                      <b-form-checkbox id="checkbox-2" v-model="status" name="checkbox-1" value="accepted"
                        unchecked-value="not_accepted">
                        Add Peruri Tera
                      </b-form-checkbox>
                      <b-form-checkbox id="checkbox-3" v-model="status" name="checkbox-1" value="accepted"
                        unchecked-value="not_accepted">
                        Final Sign ?
                      </b-form-checkbox>
                    </div>
                  </div>
                  <div class="row mt-5" style="height:115vh">
                    <div class="col-md-12 " style="margin-top:auto">

                      <b-form-checkbox id="checkbox-1" v-model="status" name="checkbox-1" value="accepted"
                        unchecked-value="not_accepted">
                        I accept the terms and condition
                      </b-form-checkbox>

                      <div class="row">
                        <div class="col-md-12">
                          <button @click="gotohistory()" class="btn btn-success btn-block">SIGN</button>
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
        this.$swal('SAVED','Your Document will be saved on Digital Locker', 'success');
        this.modal = false;
      },
       gotohistory() {
            this.upload = false;
            this.$router.push({
              path: `/Perisai/History`,
            })
          },
    },
  }

</script>
<style>

</style>
