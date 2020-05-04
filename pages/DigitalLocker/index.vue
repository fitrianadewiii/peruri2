<template>
  <section>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <div class="container ">
      <div class="row justify-content-center align-items-center mt-5" style="">
        <div class="col-md-12 ">
          <b-breadcrumb :items="items"></b-breadcrumb>
          <div class="card " style="height:100%;">
            <div class="" v-if="notempty">
              <div class="row" style="height:100%">
                <div class="col-md-12 justify-content-center align-items-center p-5">
                  <img class="image bounce-2" src="/img/file.png" style=" width :150px;display: block; margin: auto;">
                </div>
              </div>
              <div class="row">
                <div class="col-md-12 justify-content-center align-items-center text-center">
                  <p><b>Selected file: {{ file2 ? file2.name : '' }}</b></p>
                </div>
              </div>
            </div>
            <div class="" v-if="empty">
              <div class="row" style="height:100%">
                <div class="col-md-12 justify-content-center align-items-center">
                  <img class="image bounce-2 " src="/img/Empty.png" style="display: block; margin: auto;">
                </div>
              </div>
              <div class="row">
                <div class="col-md-12 justify-content-center align-items-center text-center">
                  <p><b>Your Locker is Empty !</b></p>
                </div>
              </div>
            </div>
            <div class="row">
              <div class="col-md-12 justify-content-center align-items-center text-center">
                <p>Drag or <button @click="browse" type="button" class="btn btn-info"> Browse  <b-form-file v-model="file2" class="mt-3" plain></b-form-file></button> Your Document Here </p>
                
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
  // import breadcrumb from '@@/components/breadcrumb'
  export default {
    layout: 'home',
    components: {

    },
    data() {
      return {
        empty:true,
        notempty:false,
        file2: null,
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
    },
    methods: {
       browse() {
        this.empty=false;
        this.notempty=true;
      },
    },

  }

</script>
<style>
  .image {
    animation-duration: 2s;
    animation-iteration-count: initial;
    margin: 0 auto 0 auto;
    transform-origin: bottom;
  }

  .bounce-2 {
    animation-name: bounce-2;
    animation-timing-function: ease;
  }

  @keyframes bounce-2 {
    0% {
      transform: translateY(0);
    }

    50% {
      transform: translateY(15px);
    }

    100% {
      transform: translateY(0);
    }
  }
  input {
     position: absolute;
    font-size: 50px;
    opacity: 0;
    right: 0;
    top: 0;
    cursor: pointer;
  }


</style>
