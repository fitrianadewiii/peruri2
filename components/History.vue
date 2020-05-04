<template>
  <section>
    <div class="row">
      <div class="col-md-12">
        <div class="card">         
          <div class="card-body">
            <div class="row">
                <div class="col-md-12">
                    <p><b> <b-icon icon="clock-history" variant="secondary" class="mr-2"></b-icon> History</b></p>
                    <hr>
                </div>
            </div>
            <div class="row">
              <div class="col-md-2" style="font-size: 2rem;">
                <b-icon icon="upload" class="rounded-circle bg-secondary p-2" variant="light"></b-icon>
              </div>
              <div class="col-md-10">
                  <div class="row ml-2">
                      <p><b>UPLOAD</b>
                        <br>
                     Friday, 5 jult 2019 10:00 AM</p>
                  </div>
              </div>
            </div>
             <div class="row">
              <div class="col-md-2" style="font-size: 2rem;">
                <b-icon icon="person-check-fill" class="rounded-circle bg-secondary p-2" variant="light"></b-icon>
              </div>
              <div class="col-md-10">
                  <div class="row ml-2">
                      <p><b>Verification</b>
                        <br>
                     Friday, 5 jult 2019 10:00 AM</p>
                  </div>
              </div>
            </div>
             <div class="row">
              <div class="col-md-2" style="font-size: 2rem;">
                <b-icon icon="check-all" class="rounded-circle bg-secondary p-2" variant="light"></b-icon>
              </div>
              <div class="col-md-10">
                  <div class="row ml-2">
                      <p><b>SUCCESS</b>
                        <br>
                     Friday, 5 jult 2019 10:00 AM</p>
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
import Vue from 'vue'
import { BootstrapVue, BootstrapVueIcons } from 'bootstrap-vue'

Vue.use(BootstrapVue)
Vue.use(BootstrapVueIcons)
export default {
    
}
</script>
