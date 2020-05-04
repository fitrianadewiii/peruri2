<template>
  <section>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <div class="container ">
      <div class="row justify-content-center align-items-center mt-5 " >
        <div class="col-md-12 mt-5 ">
          <div class="card p-5" style="height:100%;">
            <div class="row" style="height:100%">
              <div class="col-md-12 justify-content-center align-items-center">
                <img class="image bounce-2 " src="/img/triangle.png" style=" height: 100px;display: block; margin: auto;">
              </div>
            </div>
            <div class="row mt-2">
              <div class="col-md-12 justify-content-center align-items-center text-center">
                <p class="text-danger mt-3"><b>Warning !</b></p>
                <p ><b>For Perisai Service <br>Please Upgrade Your Account</b></p>
              </div>
            </div>
            <div class="row mt-2">
              <div class="col-md-12 justify-content-center align-items-center text-center">
                <b-button type="button" href="/Perisai/DetailUpgradeAkun" class="btn btn-info ">Upgrade</b-button>
               
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
    

  }

</script>
<style scoped>

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
  .wizard__body__step {
    height: 70vh;
    overflow-y: auto;
}

</style>
