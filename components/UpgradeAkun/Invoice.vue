<template>
  <section>
     <div class="row justify-content-center align-items-center text-center"  v-if="invoice" >
      <div class="col-md-12 ">
        <div class="row text-center">
          <div class="col-md-12">
            <h4>INVOICE</h4>
          </div>
        </div>
        <div class="row">
          <div class="col-md-12">
            <hr>
          </div>
        </div>
        <div class="row mt-2">
          <div class="col-md-6 col-sm-12 ">
            <p><b>Kepada : Sdr. Husna Aydenta</b></p>
          </div>
          <div class="col-md-6 col-sm-12 ">
            <p><b>Order ID : 123456</b></p>
            <p><b>Date : 27 / 04 /2020</b></p>
          </div>
        </div>
        <div class="row mt-2">
          <div class="col-md-8 table-responsive">
            <table class="table">
              <thead class="thead-dark">
                <tr>
                  <th scope="col">No</th>
                  <th scope="col">Nama Pesanan</th>
                  <th scope="col">Quantity</th>
                  <th scope="col">Harga</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <th scope="row">1</th>
                  <td>Platinum Plan</td>
                  <td>1</td>
                  <td>Rp. 50.000</td>
                </tr>
              </tbody>
            </table>
          </div>
          <div class="col-md-4">
            <b-button type="button" v-b-modal.modal-1 class="btn btn-info m-1" variant="">Tambah Kode Promo
            </b-button>
          </div>

        </div>
        <div class="row mt-3">
          <div class="col-md-12 text-left">
            <h5>Select Payment Method</h5>
          </div>
        </div>
        <div class="row mt-2">
          <div class="col-md-12">
            <hr>
            <div class="scrolling-wrapper row flex-row flex-nowrap">

              <div class="col-3">
                <div class="card card-block">
                  <div class="card-body text-center">
                    <img src="/img/pay1.PNG" alt="">
                  </div>
                </div>
              </div>
              <div class="col-3">
                <div class="card card-block">
                  <div class="card-body text-center">
                    <img src="/img/pay2.PNG" alt="">
                  </div>
                </div>
              </div>


            </div>
          </div>
        </div>

        <div class="row mt-3 mb-2">
          <div class="col-md-12 text-right">
            <button @click="buttonpembayaran()" class="btn btn-primary">Submit</button>
            <small>
              <p><b>klik submit before klik button next</b></p>
            </small>
          </div>
        </div>
      </div>
    </div>

    <div v-if="pembayaran" class="row justify-content-center align-items-center text-center">
      <div class="col-md-12">
        <Pembayaran />
      </div>
    </div>


  </section>
</template>
<script>
  import Pembayaran from '@@/components/UpgradeAkun/Pembayaran'
  export default {
    components: {
      //   WebCam
      Pembayaran

    },
    data() {
      return {
        pembayaran: false,
        invoice: true


      }
    },
    methods: {
        buttonpembayaran() {
        this.pembayaran = true;
        this.invoice = false;

      },

    }
  }

</script>
<style>


</style>
