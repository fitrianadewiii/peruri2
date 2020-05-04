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
              <div v-if="option" class="row mt-5 mb-5 ">
                <div class="col-md-6">
                  <div class="row justify-content-center align-items-center">
                    <div class="col-md-8">
                      <div class="card card-block m-2"  @click="buttonupload()">
                        <div class="card-body text-center">
                          <img src="/img/Single.PNG" style="height:150px" alt="">
                          <p class="mt-2"><b>Single Sign</b></p>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
                <div class="col-md-6">
                  <div class="row justify-content-center align-items-center">
                    <div class="col-md-8">
                      <div class="card card-block m-2"  @click="buttonuploadmulti()">
                        <div class="card-body text-center">
                          <img src="/img/Multiple.PNG" style="height:150px" alt="">
                          <p class="mt-2"><b>Multiple Sign</b></p>
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
                          <input type="file" class="form-control" multiple="">
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
               <div v-if="uploadmulti" class="row mt-5 mb-5 justify-content-center align-items-center">
                <div class="col-md-8">
                  <div class="card">
                    <div class="card-body">
                      <form method="post" action="#" id="#">
                        <div class="form-group files color">
                          <label>Upload Your File </label>
                          <input type="file" class="form-control" multiple="">
                        </div>
                        <div class="row text-center ">
                          <div class="col-md-12">
                            <button @click="gotomulti()" class="btn btn-secondary">Submit Document</button>
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
         uploadmulti: false,
        option: true,
        items: [{
            text: 'Perisai',
            href: '/Perisai'
          },
          //   {
          //     text: 'HomePage',
          //     href: '#'
          //   },

        ],
        
      }
    },
     methods: {
          buttonupload() {
            this.upload = true;
            this.option = false;
          },
           buttonuploadmulti() {
            this.uploadmulti = true;
            this.option = false;
            this.upload=false;
          },
          gotoHome() {
            this.upload = false;
            this.$router.push({
              path: `/Perisai/UploadDocument`,
            })
          },
           gotomulti() {
            this.uploadmulti = false;
            this.$router.push({
              path: `/Perisai/UploadDocumentMulti`,
            })
          },
    },
  }

</script>
