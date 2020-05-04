<template>
  <section>
    <div class="row">
      <div class="col-12 table-responsive">
        <table class="table table-hover">
          <thead>
            <tr class="text-center">
              <th scope="col">No</th>
              <th scope="col">Name</th>
              <th scope="col">Date</th>
              <th scope="col">Participant</th>
              <th scope="col"></th>
              <th scope="col"></th>
            </tr>
          </thead>
          <tbody>
            <tr class="text-center" style="vertical-align:middle">
              <th scope="row">1</th>
              <td>docsatu.pdf</td>
              <td>05/07/2019 10:00AM</td>
              <td>Dwi, Hana, Dina</td>
              <td> <b-button variant="info"  v-b-tooltip.hover title="forward" >
                  <b-icon icon="box-arrow-in-up-right" aria-hidden="true"></b-icon>
                </b-button></td>
              <td style="font-size: 1rem;"> 
                <b-button variant="outline-secondary"  v-b-tooltip.hover title="Download" >
                  <b-icon icon="download" aria-hidden="true"></b-icon>
                </b-button>
                <b-button variant="outline-secondary"  v-b-tooltip.hover title="print" >
                  <b-icon icon="file-earmark" aria-hidden="true"></b-icon>
                </b-button>
                <b-button variant="outline-secondary" >
                  <b-icon icon="bookmark-check" aria-hidden="true"></b-icon>
                </b-button>
              </td>
            </tr>           
          </tbody>
        </table>
      </div>
    </div>
  </section>
</template>
