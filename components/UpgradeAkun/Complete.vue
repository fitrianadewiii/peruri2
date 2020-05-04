<template>
  <section>
    <div class="row mt-5">
        <div class="col-md-12 text-center">
            <img src="/img/complete.png" style="width:150px" alt="">
        </div>
    </div>
    <div class="row mt-3">
        <div class="col-md-12 text-center">
            <h5 class=" mr-5"><b>Congratuliations</b></h5>
            <p class=" mr-5"><b> Your certificated has benn sent to your email</b> </p>            
        </div>
    </div>
    <div class="row mt-2">
        <div class="col-md-12 text-right">
          <hr>
          <b-button @click="gotoperisai()" type="button" class="btn btn-info m-1" variant="">OK, go to Perisai
          </b-button>
        </div>
      </div>
   
    
  </section>
</template>
<script>
export default {
    methods: {
       gotoperisai() {
         this.upload = false;
        this.$router.push({
          path: `/Perisai`,
        })
      },
    },
}
</script>
<style>
    
</style>
