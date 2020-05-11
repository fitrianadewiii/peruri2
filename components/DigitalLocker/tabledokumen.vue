<template>
  <section>
    <b-row>
      <b-col cols="12" md="12" class="table-responsive">
        <b-row class="mt-2">
          <b-col class="text-right">
            <b-dropdown class="mb-4" text="Add Document">
              <b-dropdown-item v-b-modal.modal-2 @click="openmodal2()">
                <b-icon icon="plus" aria-hidden="true"></b-icon> Add Folder
              </b-dropdown-item>
              <b-dropdown-item v-b-modal.modal-1 @click="openmodal()">
                <b-icon icon="plus" aria-hidden="true"></b-icon> Add File
              </b-dropdown-item>
            </b-dropdown>
            <!-- MODAL ADD FILE -->
            <b-modal v-if="modal" id="modal-1" title="Add File" hide-footer="true">
              <b-row>
                <b-col>
                  <b-form-file v-model="file2" :state="Boolean(file)" placeholder="Choose a file or drop it here..."
                    drop-placeholder="Drop file here..."></b-form-file>
                  <div class="mt-3">Selected file: {{ file2 ? file2.name : '' }}</div>
                </b-col>
              </b-row>
              <b-row>
                <b-col class="text-right">
                  <hr>
                  <b-button variant="primary" @click="closemodal()"> Add File</b-button>
                </b-col>
              </b-row>
            </b-modal>
            <!-- MODAL ADD FOLDER -->
            <b-modal v-if="modal2" id="modal-2" title="Add Folder" hide-footer="true">
              <b-row>
                <b-col>
                  <b-form-group id="input-group-1" label="Folder Name" label-for="input-1"
                    description="write your folder name">
                    <b-form-input id="input-1"  type="text" required placeholder="Folder Name">
                    </b-form-input>
                  </b-form-group>
                </b-col>
              </b-row>
              <b-row>
                <b-col class="text-right">
                  <hr>
                  <b-button variant="primary" @click="closemodal2()"> Add New Folder</b-button>
                </b-col>
              </b-row>
            </b-modal>
          </b-col>
        </b-row>
        <table class="table table-hover">
          <thead>
            <tr class="text-center">
              <th scope="col">No</th>
              <th scope="col">Name</th>
              <th scope="col">Date Modified</th>
              <th scope="col">Type</th>
              <th scope="col">Size</th>
              <th></th>
            </tr>
          </thead>
          <tbody>
            <tr  v-if="addfolder" class=" image bounce-2  text-center " style="vertical-align:middle"
              v-b-tooltip.hover="{ variant: 'secondary' }" title="view folder" @click="gotodetailfolder">
              <th scope="row">#</th>
              <td style="font-size:1.5rem;" class="text-left ">
                <b-icon icon="folder-fill" class=" rounded  mr-2" variant="info"></b-icon> ISO
              </td>
              <td>11/05/09 15:09AM</td>
              <td><b>Folder</b> </td>
              <td>10 mb </td>
              <td >
                  <b-button variant="outline-secondary">
                  <b-icon icon="files" aria-hidden="true"> details</b-icon>
                </b-button>
              </td>
            </tr>
            <tr  @click="gotofile()" v-b-tooltip.hover="{ variant: 'secondary' }" title="detail document" class="text-center"
              style="vertical-align:middle" v-for="(item, i) in history" :key="i">
              <th scope="row">{{item.no}}</th>
              <td class="text-left ">{{item.namadok}}</td>
              <td>{{item.timestamp}}</td>
              <td>{{item.type}} </td>
              <td>{{item.size}} </td>
              <td>
                <b-button v-b-popover.hover="popoverConfig" variant="outline-secondary">
                  <b-icon icon="info" aria-hidden="true"></b-icon>
                </b-button>
                <b-button v-b-popover.hover="popoverConfig2" variant="outline-secondary">
                  <b-icon icon="clock" aria-hidden="true"></b-icon>
                </b-button>
              </td>
            </tr>
          </tbody>
        </table>
      </b-col>
      <!-- <b-col cols="12" md="3">
          <b-row>
              <b-col>
                  <detail/>
              </b-col>
          </b-row>
      </b-col> -->
    </b-row>

  </section>
</template>
<script>
  import detail from '@@/components/DigitalLocker/Detail'
  export default {
    components: {
      detail
    },
    data() {
      return {
        file2: null,
        modal: true,
        modal2: true,
        addfolder: false,
        history: [{
            no: 1,
            timestamp: '2020-04-15 11:10:40.209997',
            namadok: 'a4-1.pdf',
            type: 'Docx',
            size: '100kb'

          },
          {
            no: 2,
            timestamp: '2020-04-15 11:10:40.209997',
            namadok: 'wfh-pengumumanv1.pdf',
            type: 'Docx',
            size: '100kb'

          },
          {
            no: 3,
            timestamp: '2020-04-15 11:10:40.209997',
            namadok: 'wfh-pengumumanv1.pdf',
            type: 'pdf',
            size: '100kb'

          },
          {
            no: 4,
            timestamp: '2020-04-15 11:10:40.209997',
            namadok: 'jadwal-pengumumanv3.pdf',
            type: 'Exe',
            size: '310kb'

          },
          {
            no: 5,
            timestamp: '2020-04-15 11:10:40.209997',
            namadok: 'terusanbod-pengumumankebe...',
            type: 'Docx',
            size: '1MB'
          },
        ],
      }
    },
    computed: {
      popoverConfig() {
        // Both title and content specified as a function in this example
        // and will be called the each time the popover is opened
        return {
          html: true,
          title: () => {
            // Note this is called only when the popover is opened
            return 'Detail'
          },
          content: () => {
            // Note this is called only when the popover is opened
            return '<div class="row">' +
              '<div class="col-md-12 table-responsive">' +
              '<table class="table table-borderless">' +
              '<tbody>' +
              '<tr>' +
              '<th scope="row">Timestamp</th>' +
              '<td>Jul 8,2019 08:57</td>' +
              '</tr>' +
              '<tr>' +
              '<th scope="row">Reason</th>' +
              '<td>Saya Setuju</td>' +
              '</tr>' +
              '<tr>' +
              '<th scope="row">ID</th>' +
              '<td>adsere12345</td>' +
              '</tr>' +
              '<tr>' +
              '<th scope="row">Page</th>' +
              '<td>3</td>' +
              '</tr>' +
              '<tr>' +
              '<th scope="row">Algorithm</th>' +
              '<td>SA512</td>' +
              '</tr>' +

              '</tbody>' +
              '</table>' +
              '</div>' +
              '</div>'
          }
        }
      },
      popoverConfig2() {
        // Both title and content specified as a function in this example
        // and will be called the each time the popover is opened
        return {
          html: true,
          title: () => {
            // Note this is called only when the popover is opened
            return 'History'
          },
          content: () => {
            // Note this is called only when the popover is opened
            return '<div class="row">' +
              '<div class="col-md-10">' +
              '<div class="row ml-2">' +
              '<p><b>UPLOAD</b>' +
              '<br>' +
              'Friday, 5 jult 2019 10:00 AM</p>' +
              '</div>' +
              '</div>' +
              '</div>' +
              '<div class="row">' +

              '<div class="col-md-10">' +
              '<div class="row ml-2">' +
              '<p><b>Verification</b>' +
              '<br>' +
              'Friday, 5 jult 2019 10:00 AM</p>' +
              '</div>' +
              '</div>' +
              '</div>' +
              '<div class="row">' +

              '<div class="col-md-10">' +
              '<div class="row ml-2">' +
              '<p><b>SUCCESS</b>' +
              '<br>' +
              'Friday, 5 jult 2019 10:00 AM</p>' +
              '</div>' +
              '</div>' +
              '</div>'
          }
        }
      },

    },
    methods: {
      gotodetailfolder() {
        this.$router.push({
          path: `/DigitalLocker/DetailFolder`,
        })
      },
       gotofile() {
        this.$router.push({
          path: `/DigitalLocker/DetailFile`,
        })
      },
      closemodal() {
        this.modal = false;
      },
      openmodal() {
        this.modal = true;
      },
      closemodal2() {
        this.modal2 = false;
        this.addfolder=true;
      },
      openmodal2() {
        this.modal2 = true;
        
      }

    }
  }

</script>
<style>
  a.dropdown-item:hover {
    background: #878585b3;
  }


</style>
