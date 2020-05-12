<template>
  <section>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <div class="container ">
      <div class="row justify-content-center align-items-center mt-3" style="">
        <div class="col-md-12 ">
          <b-breadcrumb :items="items"></b-breadcrumb>
          <div class="card " style="height:100%;">
            <div class="card-body">
                <Plain/>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
  import Plain from '@@/components/DigitalDokumen/plain'
  export default {
    layout: 'home',
    components: {
     Plain
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
              text: 'Plain',
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
