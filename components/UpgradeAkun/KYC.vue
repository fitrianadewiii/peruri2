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
            <!-- <img v-if="img" src="/img/id-card.png" style="height:150px" alt=""> -->
             <div >
                <vue-web-cam style="border:light-grey 1px" ref="webcam" :device-id="deviceId"
                  width="100%" height="143px"  @error="onError"  @started="onStarted"
                  @cameras="onCameras" @camera-change="onCameraChange" v-if="cameraopen" />
                </div>
                <figure v-if="cameraresult" class="figure" width="80%" height="80%" >
                  <img :src="img" class="img-responsive"  style="width:50%"/>
                </figure>
          </div>
        </div>
        <div class="row mt-5">
          <div class="col-md-12 text-center">
            <!-- <button type="button" @click="onStart" class="btn btn-info">Open Camera </button> -->
                <button type="button"  class="btn btn-info" @click="onCapture">Capture Photo</button>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>
<script>
  
import { WebCam } from "vue-web-cam";

  export default {
    name: "App",
    components: {
     "vue-web-cam": WebCam
    },
     data() {
      return {
       img: null,
        camera: null,
        deviceId: null,
        devices: [],
        cameraopen:true,
        cameraresult:false,
        open:false,
        capture:true,
      }
    },


   computed: {
      device: function () {
        return this.devices.find(n => n.deviceId === this.deviceId);
      }
    },
    watch: {
      camera: function (id) {
        this.deviceId = id;
      },
      devices: function () {
        // Once we have a list select the first one
        const [first, ...tail] = this.devices;
        if (first) {
          this.camera = first.deviceId;
          this.deviceId = first.deviceId;
        }
      }
    },
    methods: {
     
      onCapture() {
        this.img = this.$refs.webcam.capture();
        this.cameraresult=true;
        this.cameraopen=false;
        this.capture=false;
        this.open=true
      },
      onStarted(stream) {
        console.log("On Started Event", stream);
      },
      onStopped(stream) {
        console.log("On Stopped Event", stream);
      },
      onStop() {
        this.$refs.webcam.stop();
      },
      onStart() {
        this.$refs.webcam.start();
       
       
      },
      onError(error) {
        console.log("On Error Event", error);
      },
      onCameras(cameras) {
        this.devices = cameras;
        console.log("On Cameras Event", cameras);
      },
      onCameraChange(deviceId) {
        this.deviceId = deviceId;
        this.camera = deviceId;
        console.log("On Camera Change Event", deviceId);
      }
    }
  }

</script>
<style scoped>
  input {
    position: absolute;
    font-size: 50px;
    opacity: 0;
    right: 0;
    top: 0;
    cursor: pointer;
  }

</style>
