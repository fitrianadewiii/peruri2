<template>
  <section>
    <div class="row justify-content-center align-items-center text-center">
      <div class="col-md-6 ">
        <div class="row">
          <div class="col-md-12 text-center">
            <p><b>KTP</b></p>
            <img src="/img/id-card.png" style="height:150px" alt="">
          </div>
        </div>
        <div class="row mt-5">
          <div class="col-md-12 text-center">
            <button type="button" class="btn btn-info">Upload KTP <input type="file" name="file" /></button>
          </div>
        </div>

      </div>
      <div class="col-md-6 justify-content-center align-items-center text-center">
        <div class="row">
          <div class="col-md-12 text-center">
            <p><b>Face Recognation</b></p>
            <!-- <web-cam/> -->
            <img src="/img/id-card.png" style="height:150px" alt="">
          </div>
        </div>
        <div class="row mt-5">
          <div class="col-md-12 text-center">
            <button type="button" class="btn btn-info">Open Camera <input type="file" name="file" /></button>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>
<script>
  
import { WebCam } from "vue-web-cam";

  export default {
    components: {
    //   WebCam
    }


  }

</script>
<style>
  input {
    position: absolute;
    font-size: 50px;
    opacity: 0;
    right: 0;
    top: 0;
    cursor: pointer;
  }

</style>
