<template>
  <section>
    <div class="row justify-content-center align-items-center text-center" v-if="pembayaran">
      <div class="col-md-12 ">
        <div class="row text-center">
          <div class="col-md-12">
            <h4>Pembayaran</h4>
          </div>
        </div>
        <div class="row">
          <div class="col-md-12">
            <hr>
          </div>
        </div>
        <div class="row mt-2">
          <div class="col-md-4 col-sm-12 ">
            <img src="/img/pay2.png" alt="">
          </div>
          <div class="col-md-4 col-sm-12 ">

          </div>
          <div class="col-md-4 col-sm-12 ">
            <p>supported by </p>
            <img src="/img/pay2.png" alt="">
            <img src="/img/pay2.png" alt="">
          </div>
        </div>
        <div class="row mt-3">
          <div class="col-md-12 text-left">
            <p><b>Petunjuk Pembayaran</b></p>
            <p>1. Pilih produk yang kamu inginkan, lalu klik Beli.<br>
              2. Isi form pemesanan yang terdiri dari: jumlah barang, keterangan pesanan, alamat, serta pilihan
              kurir dan paket pengiriman. Klik Beli Produk Ini.<br>
              3. Pilih Bayar untuk melanjutkan ke halaman Keranjang Belanja.<br>
              4. Pilih metode pembayaran Transfer Bank, lalu klik Checkout.<br>
              5. Pada halaman selanjutnya, pilih bank yang kamu gunakan, lalu isi nomor serta nama pemilik
              rekening. Centang Simpan nomor rekening, agar kamu tidak perlu memasukkan data lagi jika
              berbelanja kembali. Klik Bayar Sekarang</p>
          </div>
        </div>
        <div class="row mt-3 mb-2">
          <div class="col-md-12 text-right">
            <button @click="buttonsuccess()" class="btn btn-primary">Submit</button>
            <small>
              <!-- <p><b>klik submit before klik button next</b></p> -->
            </small>
          </div>
        </div>
      </div>
    </div>
    <div v-if="complete" class="row justify-content-center align-items-center text-center">
      <div class="col-md-12">
        <complete />
      </div>
    </div>
  </section>
</template>
<script>
  import complete from '@@/components/UpgradeAkun/Complete'
  export default {
    components: {
      //   WebCam
      complete

    },
    data() {
      return {
        choose: true,
        draw: false,
        upload: false,
        pembayaran:true,
        complete:false,


      }
    },
    methods: {
      buttonsuccess(){
        this.pembayaran=false;
        this.complete=true;
      }

    }
  }

</script>
<style>


</style>
