<template>
  <section>
    <b-row>
      <b-col>
        <h5>Template Dokumen</h5>
        <hr>
      </b-col>
    </b-row>
    <b-row>
      <b-col>
        <b-form-group id="input-group-2" label="Lokasi" label-for="input-2">
          <b-form-input id="input-2" type="text" required placeholder="Lokasi"></b-form-input>
        </b-form-group>
      </b-col>
    </b-row>
    <b-row>
      <b-col>
        <b-form-group id="input-group-2" label="Tanggal Surat" label-for="input-2">
          <b-form-datepicker id="example-datepicker" v-model="value" class="mb-2"></b-form-datepicker>
        </b-form-group>
      </b-col>
    </b-row>
    <b-row>
      <b-col>
        <b-form-group id="input-group-2" label="Nomor Surat" label-for="input-2">
          <b-form-input id="input-2" type="text" required placeholder="Nomor Surat"></b-form-input>
        </b-form-group>
      </b-col>
    </b-row>
    <b-row>
      <b-col>
        <b-form-group id="input-group-2" label="Sifat" label-for="input-2">
          <b-form-select id="inline-form-custom-select-pref"
            :options="[{ text: 'Choose...', value: null }, 'Penting', 'Tidak Penting']" :value="null"></b-form-select>
        </b-form-group>
      </b-col>
    </b-row>
    <b-row>
      <b-col>
        <b-form-group id="input-group-2" label="Lampiran" label-for="input-2">
          <b-form-input id="input-2" type="text" required placeholder="Lampiran"></b-form-input>
        </b-form-group>
      </b-col>
    </b-row>
    <b-row>
      <b-col>
        <b-form-group id="input-group-2" label="Perihal" label-for="input-2">
          <b-form-input id="input-2" type="text" required placeholder="Perihal"></b-form-input>
        </b-form-group>
      </b-col>
    </b-row>
    <b-row>
      <b-col>
        <b-form-group id="input-group-2" label="Kepada Yth" label-for="input-2">
          <b-form-textarea id="textarea" v-model="text" placeholder="Enter something..." rows="3" max-rows="6">
          </b-form-textarea>
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
        <button type="button"  @click="showAlert" class="btn btn-info">Simpan Sebagai Draft</button> 
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
