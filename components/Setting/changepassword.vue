<template>
  <section>
    <div class="row">
      <div class="col-12">
        <h6>Change Password</h6>
        <hr>
      </div>
    </div>
    <div class="row">
      <div class="col-8">
        <b-form @submit.stop.prevent>
          <label for="text-password">Old Password</label>
          <b-input type="password" id="text-password" aria-describedby="password-help-block"></b-input>
          <b-form-text id="password-help-block">
            Your password must be 8-20 characters long, contain letters and numbers, and must not
            contain spaces, special characters, or emoji.
          </b-form-text>
        </b-form>
        <b-form @submit.stop.prevent>
          <label for="text-password">New Password</label>
          <b-input type="password" id="text-password" aria-describedby="password-help-block"></b-input>
          <b-form-text id="password-help-block">
            Your password must be 8-20 characters long, contain letters and numbers, and must not
            contain spaces, special characters, or emoji.
          </b-form-text>
        </b-form>
        <b-form @submit.stop.prevent>
          <label for="text-password">Confirm Password</label>
          <b-input type="password" id="text-password" aria-describedby="password-help-block"></b-input>
          <b-form-text id="password-help-block">
            Your password must be 8-20 characters long, contain letters and numbers, and must not
            contain spaces, special characters, or emoji.
          </b-form-text>
        </b-form>
        <div class="row mt-2">
            <div class="col-12">
                <button @click="showAlert" class="btn btn-info btn-block">Change Password</button>
            </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>

export default {
     methods: {
         
      showAlert() {
        // Use sweetalert2
        this.$swal('SUCCESS', 'Signature has been Changed', 'success');
        this.modal = false;
       
      },
     }

}
</script>
