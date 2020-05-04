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
              <div class="row">
                <div class="col-md-12">
                  <h6> Pilih salah satu dari pilihan dibawah ini </h6>
                  <hr>
                </div>
              </div>
              <div v-if="option" class="row  mt-5 mb-5 justify-content-center align-items-center">
                <div class="col-md-6">
                  <div class="row justify-content-center align-items-center">
                    <div class="col-md-8">
                      <div class="card card-block m-2" @click="buttonupload()">
                        <div class="card-body text-center">
                          <p class="mt-2"><b>Peruri Tera</b></p>
                          <h2 class="mt-3">Rp.3000</h2>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
                <div class="col-md-6">
                  <div class="row justify-content-center align-items-center">
                    <div class="col-md-8">
                      <div class="card card-block m-2" @click="buttonupload()">
                        <div class="card-body text-center">
                          <p class="mt-2"><b>Peruri Tera</b></p>
                          <h2 class="mt-3">Rp.6000</h2>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
              <div v-if="upload" class="row mt-5 mb-5 justify-content-center align-items-center">
                <div class="col-md-8">
                  <div class="card">
                    <div class="card-body">
                      <form method="post" action="#" id="#">
                        <div class="form-group files color">
                          <label>Upload Your File </label>
                          <input  type="file" class="form-control" multiple="">
                        </div>
                        <div class="row text-center ">
                          <div class="col-md-12">
                            <button @click="gotoHome()" class="btn btn-secondary">Submit Document</button>
                          </div>
                        </div>
                      </form>
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
  export default {
    layout: 'home',
    data() {
      return {
        upload: false,
        option: true,
        items: [{
            text: 'Peruri Tera',
            href: '/PeruriTera'
          },
          //   {
          //     text: 'HomePage',
          //     href: '#'
          //   },

        ]
      }
    },
    methods: {
      buttonupload() {
        this.upload = true;
        this.option = false;
      },
      gotoHome() {
         this.upload = false;
        this.$router.push({
          path: `/PeruriTera/UploadDocument`,
        })
      },
    },
  }

</script>
