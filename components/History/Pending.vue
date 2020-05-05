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
            <tr @click="gotodetail()" class="text-center" style="vertical-align:middle" v-for="(item, i) in history"
              :key="i">
              <th scope="row">{{item.no}}</th>
              <td>{{item.namadok}}</td>
              <td>{{item.timestamp}}</td>
              <td>
                <b-icon icon="people-fill" aria-hidden="true"></b-icon> Self Sign
              </td>
              <td>               
                <b-button variant="warning">
                 Pending
                </b-button>
              </td>
              <td style="font-size: 1rem;">               
                <b-button variant="outline-secondary">
                  <b-icon icon="bookmark-check" aria-hidden="true"></b-icon>
                </b-button>
                <b-button variant="outline-success">
                  <b-icon icon="bookmark-check" aria-hidden="true"></b-icon>
                </b-button>
                <b-button variant="outline-primary">
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
<script>
  export default {
    data() {
      return {
        history: [{
            no: 1,
            timestamp: '2020-04-15 11:10:40.209997',
            namadok: 'a4-1.pdf',
            namaanggota: 'Dwi, Handa , SyahPutri'

          },
          {
            no: 2,
            timestamp: '2020-04-15 11:10:40.209997',
            namadok: 'wfh-pengumumanv1.pdf',
            namaanggota: 'Dian, Verdian , Julian'

          },
          {
            no: 3,
            timestamp: '2020-04-15 11:10:40.209997',
            namadok: 'wfh-pengumumanv1.pdf',
            namaanggota: 'Dian, Verdian , Julian'

          },
          {
            no: 4,
            timestamp: '2020-04-15 11:10:40.209997',
            namadok: 'jadwal-pengumumanv3.pdf',
            namaanggota: 'Dian, Verdian , Julian'

          },
          {
            no: 5,
            timestamp: '2020-04-15 11:10:40.209997',
            namadok: 'terusanbod-pengumumankebe...',
            namaanggota: 'Dian, Verdian , Julian'

          },
        ],
      }
    },
    methods: {
      gotodetail() {
        this.$router.push({
          path: `/Perisai/History`,
        })
      },



    }
  }

</script>
<style>
  a.dropdown-item:hover {
    background: #878585b3;
}
</style>
