<template>
  <section style="">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

    <div class="container">
      <div class="row justify-content-center align-items-center" style="height:100vh;">
        <div class="col-md-4">
          <div class="card">
            <div class="row mt-5">
              <div class="col-md-12 p-1 text-center">
                <img src="/img/logo.png" style="width:50%" alt="" >
              </div>
            </div>
            <div class="row mt-3">
              <div class="col-12 text-center">
                <p><b>SIGN IN</b></p>
              </div>
            </div>
            <div class="row mt-3  ml-3 mr-3" @click="field()">
              <div class="col-12 ">
                <div class="vert-move " v-if="klikfield">
                  <p class="text-center" style="color: #0c5460;"><b>please type your username</b></p>
                </div>
                <input name="" type="email" placeholder="useremail@gmail.co.id" required="required" autocomplete="off"
                  aria-required="true" class="form-control mt-3 form-control" id="__BVID__4">
              </div>
            </div>
            <div class="row mt-2 ml-3 mr-3" @click="password()">
              <div class="col-12 ">
                <div class="vert-move  " v-if="klikpassword">
                  <p class="text-center" style="color: #0c5460;"><b>please type your password</b></p>
                </div>
                <input name="" type="password" placeholder="your password" required="required" autocomplete="off"
                  aria-required="true" class="form-control mt-3 form-control" id="__BVID__4">
              </div>
            </div>
            <div class="row mt-2 ml-3 mr-3">
                <div class="col-md-6 col-sm-12">
                </div>
                <div class="col-md-6 col-sm-12 ">
                  <div class="form-check">
                    <!-- <input type="checkbox" class="form-check-input" id="exampleCheck1">
                    <small>
                      <p class="form-check-label" for="exampleCheck1"><b>remember me</b></p>
                    </small> -->
                  </div>
                </div>
              </div>

            <div class="row mt-3">
              <div class="col-md-12">
                <div class="row  ml-3 mr-3">
                  <div class="col-md-12">
                    <button type="button" class="btn submit btn-block " @click="gotoOTP()">SIGN IN</button>
                  </div>
                </div>
                <div class="row mt-2">
                  <div class="col-md-12 ">
                    <nuxt-link to="/forgot_password">
                      <p class="text-center" style="color:#FC7859" @click="gotoForgot()">FORGOT PASSWORD</p>
                    </nuxt-link>
                  </div>
                </div>
                <div class="row ml-3 mr-3">
                  <div class="col-md-12">
                    <hr>
                  </div>
                </div>
                <div class="row">
                  <div class="col-md-12 ">
                    <!-- <nuxt-link to="/register_upload"> -->
                      <p class="text-center" style="color:#FC7859;cursor:pointer" @click="gotoregis()">REGISTER</p>
                    <!-- </nuxt-link> -->
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
    data() {
      return {
        klikfield: false,
        klikpassword: false
      }
    },
    methods: {
      gotoOTP() {
        this.$router.push({
          path: `/home`,
        })
      },
      gotoregis() {
        this.$router.push({
          path: `/register`,
        })
      },
      field() {
        this.klikfield = true;

      },
      password() {
        this.klikpassword = true;

      },


    }
  }

</script>
<style scoped>
 
  

  div.vert-move {
    -webkit-animation: mover 1s alternate;
    animation: mover 1s 0.5 alternate;
  }

  div.vert-move {
    -webkit-animation: mover 1s alternate;
    animation: mover 1s 0.5 alternate;
  }

  @-webkit-keyframes mover {
    0% {
      transform: translateY(-10);
    }

    100% {
      transform: translateY(-10px);
    }
  }

  @keyframes mover {
    0% {
      transform: translateY(-10);
    }

    100% {
      transform: translateY(-10px);
    }
  }


  .pages--auth .box__body .form-control {
    height: 51px;
    color: #777777;
    border-radius: 1.5rem !important;
    border-color: #eeeeee !important;
    letter-spacing: 1px;
    transition: all 0.2s ease-in-out;
    padding: 0 1.25rem;
  }

  .form-control {
    display: block;
    width: 100%;
    height: calc(1.5em + 0.75rem + 2px);
    padding: 0.375rem 0.75rem;
    font-size: 1rem;
    font-weight: 400;
    line-height: 1.5;
    color: #495057;
    background-color: transparent;
    background-clip: padding-box;
    border: 1px solid #ced4da;
    border-radius: 30px;
    transition: border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
  }

  .submit {
    background: #FC7859;
    border-radius: 30px;
    color: #FFF;
    height: 41px;
  }

  .card {
    background: #FDF0E0;
    border-radius: 50px;
    border: none;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0), 0 6px 20px 0 rgba(0, 0, 0, 0.09);
  }

</style>
