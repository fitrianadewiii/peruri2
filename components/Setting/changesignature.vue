<template>
  <section>
    <div class="row">
      <div class="col-12">
        <h6>Change Signature</h6>
        <hr>
      </div>
    </div>
    <div class="row">
      <div class="col-8">
       <div class="card">
           <div class="card-body">
              <VueSignaturePad style="background:white" width="100%" height="300px" ref="signaturePad" />
           </div>
           <div class="card-footer text-right ">
              <b-button class="btn-info btn-sm " @click="undo">Undo Paraf </b-button>  
           </div>
        </div>    
       
      </div>
    </div>
    <div class="row mt-2">
        <div class="col-8">
            <button  @click="showAlert" class="btn btn-info btn-block">Change Signature</button>
        </div>
    </div>
  </section>
</template>
<script>
import Vue from 'vue';
  import VueSignaturePad from 'vue-signature-pad';

  Vue.use(VueSignaturePad);
export default {
  name: 'MySignaturePad',
     methods: {
          undo() {
        this.$refs.signaturePad.undoSignature();
      },
      showAlert() {
        // Use sweetalert2
        this.$swal('SUCCESS', 'Signature has been Changed', 'success');
        this.modal = false;
       
      },
     }

}
</script>
