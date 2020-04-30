<template>
  <section>
    <div class="container">
        <div class="row justify-content-center align-items-center">
            <div class="col-md-12 mt-3">
                <b-breadcrumb :items="items"></b-breadcrumb>
            </div>
        </div>
      <div class="row mt-5 " >
        <div class="col-md-6">
          <div class="row justify-content-center align-items-center">
            <div class="col-md-8">
              <div class="card card-block m-2">
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
              <div class="card card-block m-2">
                <div class="card-body text-center">
                  <img src="/img/Multiple.PNG" style="height:150px" alt="">
                  <p class="mt-2"><b>Multiple Sign</b></p>
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
        items: [{
            text: 'Digital Locker',
            href: '#'
          },
          //   {
          //     text: 'HomePage',
          //     href: '#'
          //   },

        ]
      }
    }
  }

</script>
