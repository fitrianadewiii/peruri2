<template>
  <section>
    <div class="row">
      <div class="col-12 table-responsive">
        <table class="table table-hover">
          <thead>
            <tr class="text-center">
              <th scope="col">No</th>
              <th scope="col">Timestamp</th>
              <th scope="col">No Kop</th>
              <th scope="col">Subyek</th>
              <th scope="col">Tipe Dokumen</th>
              <th scope="col">Status</th>
              <th scope="col">Edit</th>
              <th scope="col">Hapus</th>
              <th scope="col">Lihat</th>
            </tr>
          </thead>
          <tbody>
            <tr class="text-center" style="vertical-align:middle" v-for="(item, i) in history"
              :key="i">
              <th scope="row">{{item.no}}</th>
              <td>{{item.timestamp}}</td>
              <td>{{item.nokop}}</td>
              <td>{{item.subyek}}</td>
              <td>{{item.tipedok}}</td>
              <td>{{item.status}}</td>
              <td style="font-size: 1rem;">
                <b-button variant="outline-info" v-b-tooltip.hover title="Edit">
                  <b-icon icon="pencil-square" aria-hidden="true"></b-icon>
                </b-button>
              </td>
              <td style="font-size: 1rem;">
                <b-button variant="outline-danger" v-b-tooltip.hover title="Hapus">
                  <b-icon icon="trash-fill" aria-hidden="true"></b-icon>
                </b-button>
              </td>
              <td style="font-size: 1rem;">
                <b-button  @click="gotoedit()" variant="outline-warning" v-b-tooltip.hover title="Lihat">
                  <b-icon icon="search" aria-hidden="true"></b-icon>
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
            nokop: '123645',
            subyek: 'surat tugas',
            tipedok: 'TEMPLATE',
            status: 'draft'
          },
          {
            no: 2,
            timestamp: '2020-04-15 11:10:40.209997',
            nokop: '123645',
            subyek: 'surat tugas',
            tipedok: 'TEMPLATE',
            status: 'draft'
          },
          {
            no: 3,
            timestamp: '2020-04-15 11:10:40.209997',
           nokop: '123645',
            subyek: 'surat tugas',
            tipedok: 'TEMPLATE',
            status: 'draft'

          },
          {
            no: 4,
            timestamp: '2020-04-15 11:10:40.209997',
           nokop: '123645',
            subyek: 'surat tugas',
            tipedok: 'TEMPLATE',
            status: 'draft'
          },
          {
            no: 5,
            timestamp: '2020-04-15 11:10:40.209997',
            nokop: '123645',
            subyek: 'surat tugas',
            tipedok: 'TEMPLATE',
            status: 'draft'
          },
        ],
      }
    },
    methods: {
      gotoedit() {
        this.$router.push({
          path: `/DigitalDokumen/Plain`,
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
