<template>
  <section>
    <div class="container">
      <div class="row justify-content-center align-items-center ">
        <div class="col-md-12">
          <div class="card mt-6" style="background: #FDF0E0;">
            <div class="card-body">
              <div class="row">
                <div class="col-md-6" style="border-right: 1px solid #80808057;">
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
                    <div class="row mt-2 text-center">
                      <div class="col-md-12">
                        <p class="text-danger">Your Certificate is Expired from 12 February 2020 14:00:34 AM</p>
                      </div>
                    </div>
                    <div class="row mt-2 text-center">
                      <div class="col-md-12">
                        <b-button class="btn btn-secondary">Revoke</b-button>
                        <b-button v-b-modal.modal-1 class="btn btn-success">Renew</b-button>
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

    <!-- MODAL -->
    <b-modal id="modal-1" size="lg" hide-footer="true" title="Renew Certificate">
      <b-form>
        <div class="row m-1">
          <div class="col-md-6">
            <b-form-input id="input-1" type="email" required placeholder="Enter email">
            </b-form-input>
          </div>
          <div class="col-md-6">
            <b-form-input id="input-1" type="email" required placeholder="Enter email">
            </b-form-input>
          </div>
        </div>
        <div class="row m-1">
          <div class="col-md-6">
            <b-form-input id="input-1" type="email" required placeholder="Enter email">
            </b-form-input>
          </div>
          <div class="col-md-6">
            <b-form-input id="input-1" type="email" required placeholder="Enter email">
            </b-form-input>
          </div>
        </div>
        <div class="row m-1">
          <div class="col-md-6">
            <b-form-input id="input-1" type="email" required placeholder="Enter email">
            </b-form-input>
          </div>
          <div class="col-md-6">
            <b-form-input id="input-1" type="email" required placeholder="Enter email">
            </b-form-input>
          </div>
        </div>
        <div class="row m-1">
          <div class="col-md-6">
            <b-form-input id="input-1" type="email" required placeholder="Enter email">
            </b-form-input>
          </div>
          <div class="col-md-6">
            <b-form-input id="input-1" type="email" required placeholder="Enter email">
            </b-form-input>
          </div>
        </div>
        <div class="row m-1">
          <div class="col-md-6">
            <b-form-input id="input-1" type="email" required placeholder="Enter email">
            </b-form-input>
          </div>
          <div class="col-md-6">
            <b-form-input id="input-1" type="email" required placeholder="Enter email">
            </b-form-input>
          </div>
        </div>
        <div class="row m-1">
          <div class="col-md-6">
            <b-form-input id="input-1" type="email" required placeholder="Enter email">
            </b-form-input>
          </div>
          <div class="col-md-6">
            <b-form-input id="input-1" type="email" required placeholder="Enter email">
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
                <button type="button" class="btn btn-info">Upload KTP <input class="ipt" type="file" name="file" /></button>
              </div>
            </div>

          </div>
          <div class="col-md-6 text-center">
            <div class="row">
              <div class="col-md-12 text-center">
                <p><b>Face Recognation</b></p>
                <!-- <web-cam/> -->
                <img src="/img/id-card.png" style="height:150px" alt="">
              </div>
            </div>
            <div class="row mt-5">
              <div class="col-md-12 text-center">
                <button type="button" class="btn btn-info">Open Camera <input class="ipt" type="file" name="file" /></button>
              </div>
            </div>

          </div>
        </div>
        <div class="row mt-3 mb-3 ">
          <div class="col-md-12 text-right">
            <hr>
            <button class="btn btn-primary">Submit</button>
          </div>
        </div>


      </b-form>
    </b-modal>
  </section>
</template>
<script>
  export default {
    layout: 'home'
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
