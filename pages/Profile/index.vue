<template>
  <section>
    <div class="container">
      <div class="row justify-content-center align-items-center ">
        <div class="col-md-12">
          <div class="card mt-6" style="background: #FDF0E0;">
            <div class="card-body">
              <div class="row">
                <div class="col-md-6" style="border-right: 1px solid #80808057;">
                  <div v-if="revokedata">
                  <div class="row ">
                    <div class="col-md-6 text-right">
                      <p><b>Serial Number</b></p>
                    </div>
                    <div class="col-md-6 text-left">
                      <p>SDHJ12830902901</p>
                    </div>
                  </div>
                  <div class="row">
                    <div class="col-md-12 text-center table-responsive">
                      <table class="table table-borderless">
                        <thead>
                          <tr>
                            <th scope="col">Subject DN</th>
                            <th scope="col">Issuer</th>
                          </tr>
                        </thead>
                        <tbody>
                          <tr>
                            <td>C = ID</td>
                            <td>C = ID</td>
                          </tr>
                          <tr>
                            <td>S = Jawa Timur</td>
                            <td>O = Peruri</td>
                          </tr>
                          <tr>
                            <td>C = ID</td>
                            <td>C = ID</td>
                          </tr>
                          <tr>
                            <td>S = Jawa Timur</td>
                            <td>O = Peruri</td>
                          </tr>
                          <tr>
                            <td>C = ID</td>
                            <td>C = ID</td>
                          </tr>
                          <tr>
                            <td>S = Jawa Timur</td>
                            <td>O = Peruri</td>
                          </tr>

                        </tbody>
                      </table>
                    </div>
                  </div>
                  <div class="row ">
                    <div class="col-md-12">
                      <hr>
                    </div>
                  </div>
                  </div>
                </div>
                <div class="col-md-6">
                  <div class="row mt-3 mb-3">
                    <div class="col-md-12 text-center">
                      <img src="/img/12.jpg" alt="" style="border-radius:50%;height:150px">
                    </div>
                  </div>
                  <div class="">
                    <div class="row ">
                      <div class="col-md-3 text-right">
                        <p><b>Feature :</b></p>
                      </div>
                      <div class="col-md-9 text-center">
                        <button type="button" class="btn btn-danger"> Perisai</button>
                        <button type="button" class="btn btn-info"> Peruri Tera</button>
                        <button type="button" class="btn btn-primary"> Digital Locker</button>
                      </div>
                    </div>
                    <div class="row mt-2 ">
                      <div class="col-md-4 text-center">
                        <p><b>Name</b></p>
                      </div>
                      <div class="col-md-8">
                        <p>Hasna</p>
                      </div>
                    </div>
                    <div class="row">
                      <div class="col-md-4  text-center">
                        <p><b>Email</b></p>
                      </div>
                      <div class="col-md-8">
                        <p>Hasna@gmail.com</p>
                      </div>
                    </div>
                    <div class="row ">
                      <div class="col-md-4 text-center">
                        <p><b>No Hp</b></p>
                      </div>
                      <div class="col-md-8">
                        <p>081232389284928</p>
                      </div>
                    </div>
                    <div class="row ">
                      <div class="col-md-4 text-center">
                        <p><b>Organization</b></p>
                      </div>
                      <div class="col-md-8">
                        <p>Perum Peruri</p>
                      </div>
                    </div>
                    <div v-if="renew">
                      <div class="row mt-2 text-center">
                        <div class="col-md-12">
                          <p class="text-danger">Your Certificate is Expired from 12 February 2020 14:00:34 AM</p>
                        </div>
                      </div>
                      <div class="row mt-2 text-center">
                        <div class="col-md-12">
                          <b-button v-b-modal.modal-2 class="btn btn-secondary">Revoke</b-button>
                          <b-button v-b-modal.modal-1 class="btn btn-success">Renew</b-button>
                        </div>
                      </div>
                    </div>
                    <div v-if="onprogress">
                      <div class="row mt-2 text-center">
                        <div class="col-md-12">
                          <b-button v-b-modal.modal-1 class="btn btn-warning text-white">Renew on progress</b-button>
                        </div>
                      </div>
                    </div>
                    <div v-if="valid">
                      <div class="row mt-2 text-center">
                        <div class="col-md-12">
                          <p class="text-danger">Your Certificate is Valid from 12 February 2020 14:00:34 AM</p>
                          <small>
                            <p class="text-success">*Pembaruan Sertifikat telah berhasil</p>
                          </small>
                        </div>
                      </div>
                    </div>
                     
                    <div v-if="revokee">
                      <div class="row mt-2 text-center">
                        <div class="col-md-12">
                         <button class="btn btn-success"> Revoke on Complete</button>
                        <small>
                          <p class="">*Mohon cek email ada untuk melihat Surat Pencabutan Surat Elektronik Anda</p>
                        </small>
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

    <!-- MODAL Renew -->
    <b-modal v-if="modal" id="modal-1" size="lg" hide-footer="true" title="Renew Certificate">
      <b-form>
        <div class="row m-1">
          <div class="col-md-6">
            <b-form-input id="input-1" type="text" required placeholder="Nama Lengkap">
            </b-form-input>
          </div>
          <div class="col-md-6">
            <b-form-input id="input-1" type="text" required placeholder="Jenis Kelamin">
            </b-form-input>
          </div>
        </div>
        <div class="row m-1">
          <div class="col-md-6">
            <b-form-input id="input-1" type="text" required placeholder="Nomor Handphone">
            </b-form-input>
          </div>
          <div class="col-md-6">
            <b-form-input id="input-1" type="text" required placeholder="NIK KTP">
            </b-form-input>
          </div>
        </div>
        <div class="row m-1">
          <div class="col-md-6">
            <b-form-input id="input-1" type="email" required placeholder="Alamat email">
            </b-form-input>
          </div>
          <div class="col-md-6">
            <b-form-input id="input-1" type="text" required placeholder="Alamat">
            </b-form-input>
          </div>
        </div>
        <div class="row m-1">
          <div class="col-md-6">
            <b-form-input id="input-1" type="text" required placeholder="Password">
            </b-form-input>
          </div>
          <div class="col-md-6">
            <b-form-input id="input-1" type="text" required placeholder="Kota">
            </b-form-input>
          </div>
        </div>
        <div class="row m-1">
          <div class="col-md-6">
            <b-form-input id="input-1" type="text" required placeholder="Tempat Lahir">
            </b-form-input>
          </div>
          <div class="col-md-6">
            <b-form-input id="input-1" type="text" required placeholder="Provinsi">
            </b-form-input>
          </div>
        </div>
        <div class="row m-1">
          <div class="col-md-6">
            <b-form-input id="input-1" type="date" required placeholder="Tanggal Lahir">
            </b-form-input>
          </div>

        </div>
        <div class="row mt-3">
          <div class="col-md-6 ">
            <div class="row">
              <div class="col-md-12 text-center">
                <p><b>KTP</b></p>
                <img src="/img/id-card.png" style="height:150px" alt="">
              </div>
            </div>
            <div class="row mt-5">
              <div class="col-md-12 text-center">
                <button type="button" class="btn btn-info">Upload KTP <input class="ipt" type="file"
                    name="file" /></button>
              </div>
            </div>

          </div>
          <div class="col-md-6 text-center">
            <div class="row">
              <div class="col-md-12 text-center">
                <p><b>Upload Foto Selfie</b></p>
                <!-- <web-cam/> -->
                <img src="/img/id-card.png" style="height:150px" alt="">
              </div>
            </div>
            <div class="row mt-5">
              <div class="col-md-12 text-center">
                <button type="button" class="btn btn-info">Open Camera <input class="ipt" type="file"
                    name="file" /></button>
              </div>
            </div>

          </div>
        </div>
        <div class="row mt-3 mb-3 ">
          <div class="col-md-12 text-right">
            <hr>
            <button @click="gotoprogress()" class="btn btn-primary">Submit</button>
          </div>
        </div>


      </b-form>
    </b-modal>

    <!-- MODAL REVOKE -->
    <b-modal id="modal-2" v-if="revoke" size="lg" title="Revoke Certificate" hide-footer="true">
      <div class="row p-2">
        <div class="col-md-12 text-center">
          <img src="/img/triangle.png" class="mb-3" style="width:15%" alt="">
          <p>Untuk melakukan pencabutan sertifikat, anda diminta untuk memenuhi semua persyaratan.text-center
            Apakah anda yakin untuk melakukan pencabutan sertifikat ?
          </p>
          <button type="button" class="btn btn-secondary">batal</button>
          <button type="button" @click="revooke2()" class="btn btn-danger">lanjutkan</button>
        </div>
      </div>
    </b-modal>
    <!-- MODAL REVOKE 2 -->
    <b-modal id="modal-3" v-if="revoke2" size="lg" hide-footer="true" title="Revoke Certificate">
      <div class="row mt-3 p-2">
        <div class="col-md-6 ">
          <div class="row">
            <div class="col-md-12 text-center">
              <p><b>KTP</b></p>
              <img src="/img/id-card.png" style="height:150px" alt="">
            </div>
          </div>
          <div class="row mt-5">
            <div class="col-md-12 text-center">
              <button type="button" class="btn btn-info">Upload KTP <input class="ipt" type="file"
                  name="file" /></button>
            </div>
          </div>
        </div>
        <div class="col-md-6 text-center">
          <div class="row">
            <div class="col-md-12 text-center">
              <p><b>Upload ScreenShot SN Certificate</b></p>
              <!-- <web-cam/> -->
              <img src="/img/id-card.png" style="height:150px" alt="">
            </div>
          </div>
          <div class="row mt-5">
            <div class="col-md-12 text-center">
              <button type="button" class="btn btn-info">Open Camera <input class="ipt" type="file"
                  name="file" /></button>
            </div>
          </div>

        </div>
      </div>
      <div class="row mt-3">
        <div class="col-md-12 text-center">
          <hr>
          <button type="button" @click="cancel2()" class="btn btn-secondary">batal</button>
          <button type="button" @click="revooke3()" class="btn btn-danger">lanjutkan</button>
        </div>
      </div>
    </b-modal>
    <!-- MODAL REVOKE 3 -->
    <b-modal id="modal-3" v-if="revoke3" size="lg" hide-footer="true" title="Revoke Certificate">
      <div class="row mt-3">
        <div class="col-md-12 text-center">
          <p>Upload Video Menggunakan Kalimat : <br>
            Saya (Nama Anda). Melakukan pengajuan pencabutan sertifikat elektronik Serial Number
            (Serial Number Anda), dengan alasan (alasan anda) * </p>
        </div>
      </div>
      <div class="row ">
        <div class="col-md-12 text-center">
          <img src="/img/id-card.png" style="height:150px" alt="">
        </div>
      </div>
      <div class="row mt-5">
        <div class="col-md-12 text-center">
          <button type="button" class="btn btn-secondary">Allow Camera <input class="ipt" type="file"
              name="file" /></button>
        </div>
      </div>
      <div class="row mt-3">
        <div class="col-md-12 text-center">
          <hr>
          <button type="button" @click="cancel3()" class="btn btn-secondary">batal</button>
          <button type="button" @click="revooke4()" class="btn btn-danger">lanjutkan</button>
        </div>
      </div>
    </b-modal>
    <!-- MODAL REVOKE 4 -->
    <b-modal id="modal-3" v-if="revoke4" size="lg" hide-footer="true" title="Revoke Certificate">
      <div class="row mt-3">
        <div class="col-md-12 text-center">
          <p>Penandatanganan Surat Permohonan Pencabutan Surat Elektronik ( Free )<br>
          </p>
        </div>
      </div>
      <div class="row ">
        <div class="col-md-8 text-center">
          <img src="/img/id-card.png" style="height:150px" alt="">
        </div>
        <div class="col-md-4 ">
          <div class="row">
            <div class="col-md-12">
              <button type="button" class="btn btn-primary">Add Signature</button>
            </div>
          </div>
          <div class="row mt-2">
            <div class="col-md-12">
              <button type="button" class="btn btn-info">Set Position</button>
            </div>
          </div>
        </div>
      </div>
      <div class="row mt-3">
        <div class="col-md-12 text-center">
          <hr>
          <button type="button" @click="cancel4()" class="btn btn-secondary">batal</button>
          <button type="button" @click="close()" class="btn btn-danger">Selesai</button>
        </div>
      </div>
    </b-modal>
  </section>
</template>
<script>
  export default {
    layout: 'home',
    data() {
      return {
        renew: true,
        onprogress: false,
        valid: false,
        modal: true,
        revoke: true,
        revoke2: false,
        revoke3: false,
        revoke4: false,
        revokee: false,
        revokedata:true,
      }
    },
    methods: {
      gotoprogress() {
        this.renew = false;
        this.onprogress = false;
        this.valid = true;
        this.modal = false;
      },
      revooke2() {
        this.revoke = false;
        this.revoke2 = true;
      },
      cancel2() {
        this.revoke2 = false;
        this.revoke = true;
      },
      cancel3() {
        this.revoke2 = true;
        this.revoke3 = false;
      },
      cancel4() {
        this.revoke3 = true;
        this.revoke4 = false;
      },
      revooke3() {
        this.revoke = false;
        this.revoke2 = false;
        this.revoke3 = true;
      },
      revooke4() {
        this.revoke = false;
        this.revoke2 = false;
        this.revoke3 = false;
        this.revoke4 = true;
      },
      close() {
        this.revoke4 = false;
        this.revokee = true;
        this.renew = false;
        this.valid = false;
        this.revokedata=false;
      },
    }
  }

</script>
<style scoped>
  .table th,
  .table td {
    /* padding: 0.2rem; */
    text-align: left;
    vertical-align: top;
    /* border-top: 1px solid #dee2e6; */
  }

  input.ipt {
    position: absolute;
    font-size: 50px;
    opacity: 0;
    right: 0;
    top: 0;
    cursor: pointer;
  }

</style>
