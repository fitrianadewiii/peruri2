<template>
  <section>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <div class="container ">
      <div class="row justify-content-center align-items-center mt-5" style="">
        <div class="col-md-12 ">
            <b-breadcrumb :items="items"></b-breadcrumb>
            <b-row align-v="end">
                <b-col cols="3" md="2" class="text-center">
                    <img src="/img/locker.png" alt="" style="width:80%">
                </b-col>
                <b-col cols="9" md="4">
                    <h5>DIGITAL LOCKER</h5>
                    <b-progress :value="value" :max="max" show-progress animated></b-progress>
                    <hr>
                </b-col>                
            </b-row>
            <b-row>
                <b-col cols="12" md="12">
                    <div class="card">
                        <div class="card-body">
                            <b-row>
                                <b-col cols="12" md="9">
                                    <b-row>

                                    </b-row>
                                    <b-row>
                                        <dokumen/>
                                    </b-row>
                                </b-col>
                                 <b-col cols="12" md="3">

                                </b-col>
                            </b-row>
                        </div>
                    </div>
                </b-col>
            </b-row>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
import dokumen from '@@/components/DigitalLocker/tabledokumen'
export default {
    layout: 'home',
    components: {
        dokumen
    },
    data() {
      return {
            value: 45,
        max: 100,
        empty:true,
        notempty:false,
        file2: null,
        items: [{
            text: 'Digital Locker',
            href: '#'
          },           
            {
              text: 'MyLocker',
              href: '#'
            },

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
