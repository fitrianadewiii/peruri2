<template>
  <section>
    <div class="container">
      <div class="row justify-content-center align-items-center">
        <div class="col-md-12 mt-3">
          <b-breadcrumb :items="items"></b-breadcrumb>
        </div>
      </div>
      <div class="row">
        <div class="col-md-12">
          <b-card no-body>
            <b-tabs card>
              <b-tab title="All" active>
                <b-card-text>All</b-card-text>
              </b-tab>
              <b-tab title="Completed">
                <b-card-text>Completed</b-card-text>
              </b-tab>
              <b-tab title="Pending">
                <b-card-text>Pending</b-card-text>
              </b-tab>
              <b-tab title="Sharing">
                <history />
              </b-tab>
            </b-tabs>
          </b-card>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
  import history from '@@/components/History/table'
  export default {
    layout: 'home',
      components: {
          history
        },
    data() {
      return {
        upload: false,
        uploadmulti: false,
        option: true,
      
        items: [{
            text: 'History',
            href: '/History'
          },
          //   {
          //     text: 'HomePage',
          //     href: '#'
          //   },

        ],

      }
    },
    methods: {
      buttonupload() {
        this.upload = true;
        this.option = false;
      },
      buttonuploadmulti() {
        this.uploadmulti = true;
        this.option = false;
        this.upload = false;
      },
      gotoHome() {
        this.upload = false;
        this.$router.push({
          path: `/Perisai/UploadDocument`,
        })
      },
      gotomulti() {
        this.uploadmulti = false;
        this.$router.push({
          path: `/Perisai/UploadDocumentMulti`,
        })
      },
    },
  }

</script>
