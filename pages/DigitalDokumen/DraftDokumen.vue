<template>
  <section>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <div class="container ">
      <div class="row justify-content-center align-items-center mt-5" style="">
        <div class="col-md-12 ">
          <b-breadcrumb :items="items"></b-breadcrumb>
          <div class="card " style="height:100%;">
            <tabledokumen/>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
  import tabledokumen from '@@/components/DigitalDokumen/tabledokumen'
  export default {
    layout: 'home',
    components: {
      tabledokumen
    },
    data() {
      return {
       
        items: [{
            text: 'Dokumen Digital',
            href: '#'
          },
           
            {
              text: 'Draft Dokumen',
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
