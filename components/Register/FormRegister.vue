<template>
  <section>
    <div class="row mt-1">
      <div class="col-md-6">
        <input placeholder="Nama Lengkap" type="text" required>
      </div>
      <div class="col-md-6">
        <input placeholder="Nomor Handphone" type="text" required>
      </div>
    </div>
    <div class="row mt-2">
      <div class="col-md-6">
        <input placeholder="Alamat Email" type="email" required>
      </div>
      <div class="col-md-6">
        <input placeholder="Password" type="password" required>
      </div>
    </div>
    <div class="row mt-2">
      <div class="col-md-6">
        <input placeholder="Tempat Lahir" type="text" required>
      </div>
      <div class="col-md-6">
        <input placeholder="Tanggal Lahir" type="date" required>
      </div>
    </div>
    <div class="row mt-2">
      <div class="col-md-6">
        <input placeholder="NIK KTP" type="text" required>
      </div>
      <div class="col-md-6">
        <input placeholder="Alamat" type="text" required>
      </div>
    </div>
    <div class="row mt-2">
      <div class="col-md-6">
        <input placeholder="Kota" type="text" required>
      </div>
      <div class="col-md-6">
        <input placeholder="Provinsi" type="text" required>
      </div>
    </div>
    <div class="row mt-3">
      <div class="col-md-12 text-right">
       <button type="button" class="btn btn-primary submit">Submit</button>
      </div>     
    </div>
  </section>
</template>
<script>
export default {
    
}
</script>
<style>
     input {
    width: 100%;
    display: block;
    border: none;
    padding: 15px 0;
    /* border-bottom: solid 1px #9C27B0; */
    -webkit-transition: all 0.3s cubic-bezier(0.64, 0.09, 0.08, 1);
    transition: all 0.3s cubic-bezier(0.64, 0.09, 0.08, 1);
    background: -webkit-linear-gradient(top, rgba(255, 255, 255, 0) 96%,rgba(143, 143, 143, 0.534) 4%);
    background: linear-gradient(to bottom, rgba(255, 255, 255, 0) 96%, rgba(143, 143, 143, 0.534) 4%);

    background-repeat: no-repeat;

  }

  input:focus,
  input:valid {
    box-shadow: none;
    outline: none;
    background-position: 0 0;
  }

  input::-webkit-input-placeholder {
    font-family: 'roboto', sans-serif;
    -webkit-transition: all 0.3s ease-in-out;
    transition: all 0.3s ease-in-out;
  }

  input:focus::-webkit-input-placeholder,
  input:valid::-webkit-input-placeholder {
    color: rgba(143, 143, 143, 0.534);
    font-size: 11px;
    -webkit-transform: translateY(-20px);
    transform: translateY(-20px);
    visibility: visible !important;
  }
  .submit{
    border-radius: 30px;
  }
</style>
