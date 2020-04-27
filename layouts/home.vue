<template>
  <div id="App" >
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <BootstrapSidebar :initial-show="initialShow" :links="links" :header="header" :footer="footer" :fa="true"
      @sidebarChanged="onSidebarChanged">
      <template v-slot:navbar>
        <b-navbar id="mainNavbar" toggleable="lg" fixed="top" type="light"
          style="background: #FDF0E0;box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.12);color:white">
          <b-navbar-nav>
            <b-nav-item>
              <img src="/img/logo.png" style="width:35%" alt="">
            </b-nav-item>
          </b-navbar-nav>
          <b-collapse id="nav-collapse" is-nav>
            <!-- Right aligned nav items -->
            <b-navbar-nav class="ml-auto">            


              <b-nav-item-dropdown right class="mr-3">
                <!-- Using 'button-content' slot -->
                <template v-slot:button-content>
                  <i class="fa fa-user mr-2"></i>Husna
                </template>
                <b-dropdown-item href="/Profile">Profile</b-dropdown-item>
                <b-dropdown-item href="#">Setting</b-dropdown-item>
                <b-dropdown-item href="/">Sign Out</b-dropdown-item>
              </b-nav-item-dropdown>
            </b-navbar-nav>
          </b-collapse>
        </b-navbar>
      </template>



      <template v-slot:content>
        <b-container style="margin-top: 56px">
          <nuxt />
        </b-container>
      </template>

    </BootstrapSidebar>
  </div>
</template>

<script>
  import Vue from 'vue'
  import BootstrapSidebar from 'vue-bootstrap-sidebar'
  // import { library } from '@fortawesome/fontawesome-svg-core'
  // import { faUserSecret } from '@fortawesome/free-solid-svg-icons'
  // import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'


  export default Vue.extend({
    name: 'App',
    components: {
      BootstrapSidebar,
      // FontAwesomeIcon
    },
    data() {
      return {
        initialShow: true,
        header: '<div class="row"><div class="col-md-12 text-center mt-5"><h2>Rp 100.000,-</h2></div></div>' +
          '<div class="card  mt-3 mb-3" style="max-width: 100%;border-radius:20px">' +
          '<div class="card-body bg-danger text-white " style="border-radius:20px">' +
          '<div class="row">' +
          '<div class="col-md-4" >' +
          '<h3 class="text-center">0</h3>' +
          '<small><p>Perisai</p></small>' +
          '</div>' +
          '<div class="col-md-3" >' +
          '<h3 class="text-center">0</h3>' +
          '<small><p>Tera</p></small>' +
          '</div>' +
          '<div class="col-md-5" >' +
          '<h3 class="text-center">0</h3>' +
          '<small><p>Dig Locker</p></small>' +
          '</div>' +
          '</div>' +
          '</div>' +
          '</div>' +
          '</div>' +

          '<div class="row"><div class="col-md-12 text-center mb-3">' +
          '<button type="button" class="btn submit btn-block "> Buy</button</div></div>',

        links: [{
            name: 'Home',
            href: {
              name: 'home'
            },
            faIcon: ['fas', 'home']
          },
          // {
          //   // name: 'Dropdown',
          //   // faIcon: ['fa', 'tint'],
          //   // children: [
          //   //   {
          //   //     name: 'Child Item 1',
          //   //     href: {
          //   //       name: 'child-item-1'
          //   //     },
          //   //     faIcon: ['fas', 'child']
          //   //   },
          //   //   {
          //   //     name: 'Child Item 2',
          //   //     href: {
          //   //       name: 'child-item-2'
          //   //     },
          //   //     faIcon: ['fas', 'child']
          //   //   }
          //   // ]
          // },
          {
            name: 'Perisai',
            href:'Perisai/UpgradeAkun',
            faIcon: 'users'
          },
          {
            name: 'Peruri Tera',
            href: {
              name: 'contact'
            },
            faIcon: 'phone'
          },
          {
            name: 'Digital Locker',
            href: {
              name: 'DigitalLocker'
            },
            faIcon: 'users'
          },
          {
            name: 'History',
            href: {
              name: 'contact'
            },
            faIcon: 'phone'
          }
        ],
      }
    },
    methods: {
      onSidebarChanged() {}
    }
  })

</script>

<style lang="scss">
  @import 'node_modules/bootstrap/scss/bootstrap';
  @import 'node_modules/bootstrap-vue/src/index.scss';
  @import 'node_modules/vue-bootstrap-sidebar/src/scss/default-theme';

  .card {

    background: #FFFFFF;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.2);
    border-radius: 10px;
    // border: none;
  }

  .card-header {
    border-radius: 10px;
  }

  nav#sidebar {
    background: #FDF0E0;
    box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.12);
  }

  .default-theme .list-group-item .sidebar-menu-item {
    /* background-color: #fff; */
    color: #495057;
    border: none;
    background: #FDF0E0;
  }

  .default-theme .sidebar-header {
    /* background-color: #fff; */
    color: #495057;
    background: #FDF0E0;
  }

  .submit {
    background: #FC7859;
    border-radius: 30px;
    color: #FFF;
    height: 41px;
  }

  .submit:hover {
    color: #FFF;
    transform: translateY(-5px);
  }

  .danger {
    background: #DA3A21;
  }

  .primary {
    background: #339CC9;
  }

  .warning {
    background: #ffb129;
  }

  .btn {
    border-radius: 30px;
  }


  .b-dropdown-item {
    background: #FC7859;
    color: white;
  }

  .b-dropdown-item:hover {
    background: #FFFFFF;
    color: grey;
  }

  .hello {
    width: 100%;
    height: 300px;
  }

  .scrolling-wrapper {
    overflow-x: auto;
    padding-top: 30px;
    padding-bottom: 70px;
  }

  .card-block {
    height: 100%;
    background-color: #fff;
    width: 100%;
    // background: linear-gradient(to left bottom, rgba(#ff4057, 0.8), rgb(51, 51, 102) 90%), url('https://source.unsplash.com/1024x1024?mountains');
    background-position: center;
    background-size: cover;
    box-shadow: 0 5px 5px hsla(240%, 43%, 40%, 0.35);
    transition: all 0.2s ease-in-out !important;

  }

  .card-block:hover {
    transform: translateY(-5px);
    box-shadow: 0 7px 7px hsla(240%, 43%, 40%, 0.5);
    cursor: pointer;
  }

 .card:hover {
    transform: translateY(-3px);
    box-shadow: 0 2px 2px hsla(240%, 43%, 40%, 0.5);
     cursor: pointer;
  }
  

</style>
