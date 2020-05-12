<template>
  <section>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <div class="container ">
      <div class="row justify-content-center align-items-center mt-3" style="">
        <div class="col-md-12 ">
          <b-breadcrumb :items="items"></b-breadcrumb>
          <div class="card " style="height:100%;">
            <div class="card-body">
                <Templatee/>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
  import Templatee from '@@/components/DigitalDokumen/template'
  export default {
    layout: 'home',
    components: {
     Templatee
    },
    data() {
      return {
       
        items: [{
            text: 'Dokumen Digital',
            href: '#'
          },           
            {
              text: 'Buat Dokumen',
              href: '#'
            },
             {
              text: 'Template',
              href: '#'
            },

        ]
      }
    },
    methods: {
      
    },

  }

</script>
<style>
 


</style>
