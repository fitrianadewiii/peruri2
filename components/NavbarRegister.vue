<template>
  <section>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <div>
      <b-navbar toggleable="lg" type="light" style="background: #FDF0E0;box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.12);">
        <b-navbar-brand href="/" v-b-toggle.sidebar-1 class="ml-3">
          <img src="/img/logo.png" alt="" style="width:35%">
        </b-navbar-brand>

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

       
      </b-navbar>
      
    </div>
  </section>
</template>
<script>
  export default {
     data(){
        return{
          menuitem:false,
          menuitem2:false,
          kliksubmenu2:false,
          kliksubmenu:false
         
        }
    },
    methods: {
      gotoHome() {
        this.$router.push({
          path: `/home`,
        })
      },
       submenu(){
        this.menuitem=true;
         this.kliksubmenu=true;
        
      },
      submenu2(){
        this.menuitem2=true;
        this.kliksubmenu2=true;
        
      },
      closemenu(){
        this.menuitem=false;
        
      },


    }
  }

</script>
<style>
 
</style>
