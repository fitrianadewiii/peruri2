<template >
  <section >
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <div class="container ">
      <div class="row ">
        <div class="col-md-3 mt-3">
          <div class="card  mb-3" style="max-width: 100%;">
            <div class="card-header text-white bg-success text-center">Success</div>
            <div class="card-body text-center" style="height:100px">
              <!-- <h5 class="card-title">Primary card title</h5> -->
              <h1>0</h1>
            </div>
          </div>
        </div>
        <div class="col-md-3 mt-3">
          <div class="card  mb-3" style="max-width: 100%;">
            <div class="card-header text-white warning text-center">Pending</div>
            <div class="card-body text-center" style="height:100px">
              <!-- <h5 class="card-title">Primary card title</h5> -->
              <h1>0</h1>
            </div>
          </div>
        </div>
        <div class="col-md-3 mt-3">
          <div class="card  mb-3" style="max-width: 100%;">
            <div class="card-header text-white danger text-center">Failed</div>
            <div class="card-body text-center" style="height:100px">
              <!-- <h5 class="card-title">Primary card title</h5> -->
              <h1>0</h1>
            </div>
          </div>
        </div>
        <div class="col-md-3 mt-3">
          <div class="card  mb-3" v-b-modal.modal-1  style="max-width: 100%; cursor:pointer">
            <div class="card-header text-white primary text-center">Certificated</div>
            <div class="card-body text-center " style="height:100px">
              <!-- <h5 class="card-title">Primary card title</h5> -->
              <p><b>See Certificate</b></p>
            </div>
          </div>
        </div>

      </div>
      <div class="row mt-3">
        <div class="col-md-8">
          <div class="hello" ref="chartdiv">
          </div>
        </div>
        <div class="col-md-4">
          <div class="card  mb-3" style="max-width: 100%;">
            <div class="card-header text-white primary text-center">Your Signature</div>
            <div class="card-body text-center">
              <img src="/img/Vector4.png" alt="">
            </div>
          </div>
        </div>
      </div>
      <div class="row mt-5">
        <div class="col-md-12">
          <h3>Recent Document</h3>
        </div>
        <hr>
      </div>
      <div class="row mt-1 mb-3">
        <div class="col-md-12">
          <hr>
          <div class="scrolling-wrapper row flex-row flex-nowrap">

            <div class="col-2">
              <div class="card card-block">
                <div class="card-body text-center">
                  <img src="/img/179483.PNG" alt="">
                  <p class="mt-1"><b>Doc1.pdf</b></p>
                </div>
              </div>
            </div>
            <div class="col-2">
              <div class="card card-block">
                <div class="card-body text-center">
                  <img src="/img/179483.PNG" alt="">
                  <p class="mt-1"><b>Doc2.pdf</b></p>
                </div>
              </div>
            </div>


          </div>
        </div>
      </div>

      <!-- MODAL -->
      <b-modal id="modal-1" size="lg" hide-footer="true" hide-header="true" title="BootstrapVue">
        <div class="row">
            <div class="col-md-12">
                <img src="/img/certificate.png" style="width:100%" alt="">
            </div>
        </div>
      </b-modal>
    </div>
  </section>
</template>

<script>
  import * as am4core from "@amcharts/amcharts4/core";
  import * as am4charts from "@amcharts/amcharts4/charts";
  import am4themes_animated from "@amcharts/amcharts4/themes/animated";

  am4core.useTheme(am4themes_animated);
  export default {
    layout: 'home',
    name: 'demo',
    components: {},
    mounted() {

      // Create chart
      let chart = am4core.create(this.$refs.chartdiv, am4charts.PieChart);
      chart.hiddenState.properties.opacity = 0; // this creates initial fade-in

      chart.data = [{
          country: "Peruri Sign",
          value: 260
        },
        {
          country: "Peruri Code",
          value: 340
        },
        {
          country: "Digital Locker",
          value: 400
        },

      ];



      let series = chart.series.push(new am4charts.PieSeries());
      series.dataFields.value = "value";
      series.dataFields.radiusValue = "value";
      series.dataFields.category = "country";
      series.slices.template.cornerRadius = 6;
      series.colors.step = 3;

      series.hiddenState.properties.endAngle = -90;

      chart.legend = new am4charts.Legend();



    },

    beforeDestroy() {
      if (this.chart) {
        this.chart.dispose();
      }
    },
    data() {
      return {
        steps: [{
            label: 'Register',
            slot: 'page1',
          },
          {
            label: 'Aktivasi',
            slot: 'page2',
          },
          {
            label: 'Complete',
            slot: 'page3',
          },
        ],
      };
    },
    methods: {
      nextClicked(currentPage) {
        console.log('next clicked', currentPage)
        return true; //return false if you want to prevent moving to next page
      },
      backClicked(currentPage) {
        console.log('back clicked', currentPage);
        return true; //return false if you want to prevent moving to previous page
      }
    },
  };

</script>
<style scoped>
  
  

</style>
