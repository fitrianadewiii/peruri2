<template>
  <section>
    <div class="row justify-content-center align-items-center text-center"  v-if="signature" >
      <div class="col-md-12 ">
        <div class="row  justify-content-center align-items-center text-center" v-if="choose">
          <div class="col-md-6 text-center ">
            <p><b>Choose Signature</b></p>
            <div class="scrolling-wrapper row flex-row flex-nowrap ">
              <div class="col-4">

                <div class="card card-block">
                  <div class="card-body text-center">
                    <img src="/img/Vector3.PNG" style="width:100%" alt="">
                  </div>
                </div>
              </div>
              <div class="col-4">
                <div class="card card-block">
                  <div class="card-body text-center">
                    <img src="/img/Vector4.PNG" style="width:100%" alt="">
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="row  justify-content-center align-items-center text-center" v-if="draw">
          <div class="col-md-6 text-center m-3">
            <p><b>draw here</b></p>
            <div class="row">
              <div class="col-md-8">
                <div class="card">
                  <VueSignaturePad style="background:white" width="100%" height="300" ref="signaturePad" />
                </div>
              </div>
              <div class="col-md-4">
                <b-button class="btn-info btn-sm " @click="undo">Undo Paraf </b-button>
              </div>
            </div>
          </div>
        </div>

        <div class="row  justify-content-center align-items-center text-center" v-if="upload">
          <div class="col-md-8 text-center m-3">
            <p><b>draw here</b></p>
            <div class="row">
              <div class="col-md-6">
                <div class="card">
                  <img src="/img/Vector3.PNG" class="p-3" style="height:150px" alt="">
                </div>
              </div>
              <div class="col-md-4">
                <b-button class="btn-info btn-sm ">Choose and Upload File </b-button>
              </div>
            </div>
          </div>
        </div>

        <div class="row mt-1 justify-content-center align-items-center text-center">
          <div class="col-md-4 text-center">
            <b-button type="button" @click="buttonchoose()" class="btn m-1" variant="outline-secondary">Choose
            </b-button>
            <b-button type="button" @click="buttondraw()" class="btn m-1" variant="outline-secondary">Draw</b-button>
            <b-button type="button" @click="buttonupload()" class="btn m-1" variant="outline-secondary">Upload
            </b-button>
          </div>
        </div>
        <div class="row mt-2">
          <div class="col-md-12 text-right">
            <hr>
            <b-button type="button" v-b-modal.modal-1 class="btn btn-info m-1" variant="">Submit
            </b-button>
            <!-- <small><p><b>Klik Submit before Next</b></p></small> -->
          </div>
        </div>
      </div>
    </div>

    <!-- MODAL -->
    <b-modal id="modal-1" size="md" hide-footer="true"  hide-header="true" title="BootstrapVue"  v-if="modal">
      <div class="row">
        <div class="col-md-12">
          <h5>Subsricber Agreement</h5>
        </div>
      </div>
      <div class="row">
        <div class="col-md-12">
          <hr>
        </div>
      </div>
      <div class="row mt-1">
        <div class="col-md-12">
          <textarea class="form-control" id="exampleFormControlTextarea1" rows="4">
           Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
         </textarea>
        </div>
      </div>
      <div class="row mt-2">
        <div class="col-md-12">
          <b-form-checkbox size="sm">Saya Telah Membaca dan Menyetujui Syarat dan Ketentuan Diatas</b-form-checkbox>
          <b-form-checkbox size="sm">Saya Telah Membaca dan Menyetujui <a href="">Subscriber Agreement</a></b-form-checkbox>
          <b-form-checkbox size="sm">Saya Telah Membaca dan Memahami <a href="">Certificate Policy</a></b-form-checkbox>
          <b-form-checkbox size="sm">Saya Telah Membaca dan Memahami <a href="">Certificate Practice Statement</a></b-form-checkbox>
        </div>
      </div>
      <div class="row mt-2 mb-2">
        <div class="col-md-12 text-right">
          <hr>
          <button class="btn btn-primary" @click="buttonsubsplan()" >OK</button>
        </div>
      </div>
    </b-modal>

    <div  v-if="subsplan" class="row justify-content-center align-items-center text-center">
      <div class="col-md-12">
        <SubsPlan/>
      </div>
    </div>

  </section>
</template>
<script>
  import Vue from 'vue';
  import VueSignaturePad from 'vue-signature-pad';
  import SubsPlan from '@@/components/UpgradeAkun/SubscriptionPlan'

  Vue.use(VueSignaturePad);
  export default {
    name: 'MySignaturePad',
    components: {
      //   WebCam
      SubsPlan

    },
    data() {
      return {
        choose: true,
        draw: false,
        upload: false,
        subsplan:false,
        signature:true,
        modal:true,


      }
    },
    methods: {
      buttonchoose() {
        this.choose = true;
        this.draw = false;
        this.upload = false;

      },
      buttondraw() {
        this.draw = true;
        this.choose = false;
        this.upload = false;
      },
      buttonupload() {
        this.upload = true;
        this.choose = false;
        this.draw = false;
      },
      undo() {
        this.$refs.signaturePad.undoSignature();
      },
      buttonsubsplan() {
        this.subsplan = true;
         this.signature = false;
         this.modal=false;
      },

    }


  }

</script>
<style>


</style>
