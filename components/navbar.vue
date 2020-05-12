<template>
  <section>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <div>
      <b-navbar toggleable="lg" type="light" style="background: #FDF0E0;box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.12);">
        <b-navbar-brand href="#" v-b-toggle.sidebar-1 class="ml-3">
          <img src="/img/logo.png" alt="" style="width:35%">
        </b-navbar-brand>

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>


          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">

            <b-nav-item class="mr-3" @click="gotoHome()">
              <i class="fa fa-home mr-2"></i>Home
            </b-nav-item>


            <b-nav-item-dropdown right class="mr-3">
              <!-- Using 'button-content' slot -->
              <template v-slot:button-content>
                <i class="fa fa-user mr-2"></i>Husna
              </template>
              <b-dropdown-item href="/Setting">Settings</b-dropdown-item>
              <b-dropdown-item href="/Profile">Profile</b-dropdown-item>
              <b-dropdown-item href="/">Sign Out</b-dropdown-item>
            </b-nav-item-dropdown>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
      <b-sidebar id="sidebar-1" shadow>
        <div class="row m-1">
          <div class="col-12 text-center">
            <img src="/img/logo.png" style="width:40%" alt="">
          </div>
        </div>
        <div class="row m-1 mt-2">
          <div class="col-md-12">
            <div class="row" style="">
              <div class="col-md-12 text-center ">
                <h3>Rp 100.000,-</h3>
              </div>
            </div>
            <div class="card " style="max-width: 100%;border-radius:20px">
              <div class="card-body bg-danger text-white " style="border-radius:20px">
                <div class="row">
                  <div class="col-md-4">
                    <h3 class="text-center">0</h3>
                    <small>
                      <p>Perisai</p>
                    </small>
                  </div>
                  <div class="col-md-3">
                    <h3 class="text-center">0</h3>
                    <small>
                      <p>Tera</p>
                    </small>
                  </div>
                  <div class="col-md-5">
                    <h3 class="text-center">0</h3>
                    <small>
                      <p>Dig Locker</p>
                    </small>
                  </div>
                </div>
              </div>
            </div>
            <div class="row mt-2 mb-2">
              <div class="col-md-12 text-center ">
                <button type="button" @click="Buy()" class="btn submit btn-block "> Buy</button></div>
            </div>
          </div>
        </div>

        <b-list-group class="">



          <!-- <nuxt-link to="/TandaTanganDigital"> -->
          <b-list-group-item button v-b-toggle.collapse-2><i class="fa fa-file mr-3"></i>Dokumen Digital <i
              class="fa fa-chevron-down ml-3 "></i>
          </b-list-group-item>
          <b-collapse id="collapse-2">
            <b-list-group-item button v-b-toggle.collapse-3><i class="fa  fa-folder ml-3 mr-3"></i>Buat Dokumen <i
                class="fa fa-chevron-down ml-3 "></i>
            </b-list-group-item>
            <b-collapse id="collapse-3">
              <b-list-group-item button  @click="Template()" ><i class="fa  fa-file ml-5 mr-3"></i>Template
              </b-list-group-item>
              <b-list-group-item button @click="Plain()"><i class="fa  fa-file ml-5 mr-3"></i>Plain
              </b-list-group-item>
            </b-collapse>
            <b-list-group-item button @click="DraftDokumen()" ><i class="fa  fa-file ml-3 mr-3"></i>Draft Dokumen
            </b-list-group-item>
          </b-collapse>


          <b-list-group-item button @click="Perisai()"><i class="fa fa-bookmark mr-3"></i>Perisai
          </b-list-group-item>
          <b-list-group-item button @click="PeruriTera()"><i class="fa  fa-calendar-check-o mr-3"></i>Peruri Tera
          </b-list-group-item>

          <b-list-group-item button @click="Digital()"><i class="fa  fa-list mr-3"></i>Digital Locker
          </b-list-group-item>
          <b-list-group-item button @click="Riwayat()"><i class="fa  fa-history mr-3"></i>History
          </b-list-group-item>

        </b-list-group>
        <div class="row mt-2 m-1">
          <div class="col-12">
            <p><b>Last Login</b></p>
            <hr>
            <p style="font-size:9px">On > 05/05/2020 04:35 AM
              <br>
              IP Adress > 109.123.123.123
              <br>
              Browser > Mozila 4.5
              <br>
            </p>
          </div>
        </div>
      </b-sidebar>
    </div>
  </section>
</template>
<script>
  export default {
    data() {
      return {
        menuitem: false,
        menuitem2: false,
        kliksubmenu2: false,
        kliksubmenu: false

      }
    },
    methods: {
       Plain() {
        this.$router.push({
          path: `/DigitalDokumen/Plain`,
        })
      },
       Template() {
        this.$router.push({
          path: `/DigitalDokumen/Template`,
        })
      },
      DraftDokumen() {
        this.$router.push({
          path: `/DigitalDokumen/DraftDokumen`,
        })
      },
      gotoHome() {
        this.$router.push({
          path: `/home`,
        })
      },
      Perisai() {
        this.$router.push({
          path: `/Perisai/UpgradeAkun`,
        })
      },
      PeruriTera() {
        this.$router.push({
          path: `/PeruriTera`,
        })
      },

      Riwayat() {
        this.$router.push({
          path: '/History'
        })
      },
      Digital() {
        this.$router.push({
          path: '/DigitalLocker'
        })
      },
      Buy() {
        this.$router.push({
          path: '/Buy'
        })
      },




    }
  }

</script>
<style>
  .b-sidebar>.b-sidebar-body {
    background: #FDF0E0;
    flex-grow: 1;
    height: 100%;
    overflow-y: hidden;
    overflow-x: hidden;

  }

  .b-sidebar>.b-sidebar-header {
    font-size: 1.5rem;
    padding: 0.2rem 0.4rem;

    display: flex;
    flex-direction: row;
    flex-grow: 0;
    align-items: center;
    background: #FDF0E0;
    color: #999999;
  }

  .list-group-item:first-child {
    border-top-left-radius: 0rem;
    border-top-right-radius: 0rem;
  }

  .list-group-item {
    position: relative;
    display: block;
    padding: 0.75rem 1.25rem;
    background-color: #FDF0E0;
    ;
    color: #999999;
    border: none;

  }

  .list-group-item.inner {
    border: transparent;
    width: 100%;
    color: #999999;
    background: #FDF0E0;
    ;
    border-left-color: #999999 solid;
  }

  .card {

    background: #FFFFFF;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.2);
    border-radius: 10px;
  }



  /* .card-header {
    border-radius: 10px;
  } */

  nav#sidebar {
    background: #FDF0E0;
    box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.12);
  }

  .default-theme .list-group-item .sidebar-menu-item {
    /* background-color: #fff; */
    color: #495057;
    border: none;
    background: #FDF0E0;
  }

  .default-theme .sidebar-header {
    /* background-color: #fff; */
    color: #495057;
    background: #FDF0E0;
  }

  .submit {
    background: #FC7859;
    border-radius: 30px;
    color: #FFF;
    height: 41px;
  }

  .submit:hover {
    color: #FFF;
    transform: translateY(-5px);
  }

  .danger {
    background: #DA3A21;
  }

  .primary {
    background: #339CC9;
  }

  .warning {
    background: #ffb129;
  }

  .btn {
    border-radius: 30px;
  }


  .b-dropdown-item {
    background: #FC7859;
    color: white;
  }

  .b-dropdown-item:hover {
    background: #FFFFFF;
    color: grey;
  }

  .hello {
    width: 100%;
    height: 300px;
  }

  .scrolling-wrapper {
    overflow-x: auto;
    padding-top: 30px;
    padding-bottom: 70px;
  }

  .card-block {
    height: 100%;
    background-color: #fff;
    width: 100%;
    background-position: center;
    background-size: cover;
    box-shadow: 0 5px 5px hsla(240%, 43%, 40%, 0.35);
    transition: all 0.2s ease-in-out !important;

  }

  .card-block:hover {
    transform: translateY(-5px);
    box-shadow: 0 0 6px #4183D7;
    cursor: pointer;

  }

  .card:hover {
    /* transform: translateY(-3px); */
    box-shadow: 0 2px 2px hsla(240%, 43%, 40%, 0.5);
    cursor: pointer;
  }

  input[type="checkbox"] {
    position: relative;
    /* top: .5em;
  left:.7em; */

  }

  @media (pointer: coarse) {
    input[type="checkbox"] {
      height: 4em;
      width: 4em;
    }
  }

  /* Use z-index to make it accessible to keyboard navigation */
  @media (hover: hover) {
    input[type="checkbox"] {
      z-index: -1
    }

    .card:hover input[type="checkbox"],
    input[type="checkbox"]:focus,
    input[type="checkbox"]:checked {
      z-index: auto
    }

  }

  .files input {
    outline: 2px dashed #92b0b3;
    outline-offset: -10px;
    -webkit-transition: outline-offset .15s ease-in-out, background-color .15s linear;
    transition: outline-offset .15s ease-in-out, background-color .15s linear;
    padding: 120px 0px 85px 35%;
    text-align: center !important;
    margin: 0;
    width: 100% !important;
  }

  .files input:focus {
    outline: 2px dashed #92b0b3;
    outline-offset: -10px;
    -webkit-transition: outline-offset .15s ease-in-out, background-color .15s linear;
    transition: outline-offset .15s ease-in-out, background-color .15s linear;
    border: 1px solid #92b0b3;
  }

  .files {
    position: relative
  }

  .files:after {
    pointer-events: none;
    position: absolute;
    top: 60px;
    left: 0;
    width: 50px;
    right: 0;
    height: 56px;
    content: "";
    background-image: url(https://image.flaticon.com/icons/png/128/109/109612.png);
    display: block;
    margin: 0 auto;
    background-size: 100%;
    background-repeat: no-repeat;
  }

  .color input {
    background-color: #f1f1f1;
  }

  .files:before {
    position: absolute;
    bottom: -10px;
    left: 0;
    pointer-events: none;
    width: 100%;
    right: 0;
    height: 57px;
    content: " or drag it here. ";
    display: block;
    margin: 0 auto;
    color: #2ea591;
    font-weight: 600;
    text-transform: capitalize;
    text-align: center;
  }

</style>
