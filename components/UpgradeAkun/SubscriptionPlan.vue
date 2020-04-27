<template>
  <section>
    <div class="row " v-if="plan">
      <div class="col-md-12 ">
        <div class="row text-center">
          <div class="col-md-12">
            <h4>Subscription Plan</h4>
          </div>
        </div>
        <div class="row">
          <div class="col-md-12">
            <hr>
          </div>
        </div>
        <div class="row mt-2">
          <div class="col-md-4">
            <div class="card">
              <div class="card-body">
                <div class="row">
                  <div class="col-md-12">
                    <p><b>BASIC</b></p>
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
                    <p>Sertificate Digital<br>
                      10x Perisai<br>
                      5mb Digital Locker</p>
                  </div>
                </div>

              </div>
            </div>
          </div>
          <div class="col-md-4">
            <div class="card">
              <div class="card-body">
                <div class="row">
                  <div class="col-md-12">
                    <p><b>SILVER</b></p>
                  </div>
                </div>
                <div class="row mt-1">
                  <div class="col-md-12">
                    <h5>40.000</h5>
                  </div>
                </div>
                <div class="row mt-1">
                  <div class="col-md-12">
                    <hr>
                  </div>
                </div>
                <div class="row mt-1">
                  <div class="col-md-12">
                    <p>Sertificate Digital<br>
                      10x Perisai<br>
                      5mb Digital Locker</p>
                  </div>
                </div>

              </div>
            </div>
          </div>
          <div class="col-md-4">
            <div class="card">
              <div class="card-body">
                <div class="row">
                  <div class="col-md-12">
                    <p><b>PLATINUM</b></p>
                  </div>
                </div>
                <div class="row mt-1">
                  <div class="col-md-12">
                    <h5>50.000</h5>
                  </div>
                </div>
                <div class="row mt-1">
                  <div class="col-md-12">
                    <hr>
                  </div>
                </div>
                <div class="row mt-1">
                  <div class="col-md-12">
                    <p>Sertificate Digital<br>
                      10x Perisai<br>
                      5mb Digital Locker</p>
                  </div>
                </div>

              </div>
            </div>
          </div>
        </div>

        <div class="row mt-2">
          <div class="col-md-12 text-right">
            <b-button type="button" @click="buttoninvoice()" class="btn btn-info m-1" variant="">Submit
            </b-button>
            <small><p><b>Klik Submit before Next</b></p></small>
          </div>
        </div>
      </div>
    </div>



    <div v-if="invoice" class="row justify-content-center align-items-center text-center" >
      <div class="col-md-12">
        <Invoice />
      </div>
    </div>

  </section>
</template>
<script>

  import Invoice from '@@/components/UpgradeAkun/Invoice'
  export default {
    name: 'MySignaturePad',
    components: {
      //   WebCam
      Invoice

    },
    data() {
      return {
        invoice: false,
        plan: true,
        modal: true,


      }
    },
    methods: {
    
      buttoninvoice() {
        this.invoice = true;
        this.plan = false;
      },

    }


  }

</script>
<style>


</style>
