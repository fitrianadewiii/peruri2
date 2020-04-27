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
  .b-sidebar>.b-sidebar-body {
    background:  #FDF0E0;
    flex-grow: 1;
    height: 100%;
    overflow-y: auto;
    overflow-x: hidden;
  }

  .b-sidebar>.b-sidebar-header {
    font-size: 1.5rem;
    padding: 2.5rem 1rem;

    display: flex;
    flex-direction: row;
    flex-grow: 0;
    align-items: center;
    background:  #FDF0E0;
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
    background-color:  #FDF0E0;;
    color: #999999;

  }

  .list-group-item.inner {
    border: transparent;
    width: 100%;
    color: #999999;
    background:  #FDF0E0;;
    border-left-color: #999999 solid;
  }
  
</style>
