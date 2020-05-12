<template>
  <section>    
    <b-row>
      <b-col>
        <b-form-group id="input-group-2" label="Judul Dokumen" label-for="input-2">
          <b-form-input id="input-2" type="text" required placeholder="Judul Dokumen"></b-form-input>
        </b-form-group>
      </b-col>
    </b-row>
  
    <b-row>
      <b-col>
        <b-form-group id="input-group-2" label="isi" label-for="input-2">
          <vue-editor v-model="content"></vue-editor>
        </b-form-group>
      </b-col>
    </b-row>
    <b-row>
      <b-col>
        <hr>
        <button type="button" class="btn submit">Submit dan Tanda Tangan</button> 
        <button type="button" @click="showAlert" class="btn btn-info">Simpan Sebagai Draft</button> 
        <button type="button" class="btn btn-secondary">PDF Preview</button>
      </b-col>
    </b-row>
  </section>
</template>
<script>
  import {
    VueEditor
  } from "vue2-editor";
  export default {
    components: {
      VueEditor
    },
    data() {
      return {
        content: "<h4>Some initial content</h4>"
      }
    },
    methods: {
         showAlert() {
        // Use sweetalert2
        this.$swal('SAVED','Your Document will be saved as a Draft', 'success');
        this.modal = false;
      },
    }
  }

</script>
<style>
  a.dropdown-item:hover {
    background: #878585b3;
  }

</style>
