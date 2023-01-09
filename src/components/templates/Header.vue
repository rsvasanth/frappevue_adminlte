<template>
      <!-- Navbar -->
      <nav class="main-header navbar navbar-expand navbar-white navbar-light">
        <!-- Left navbar links -->
        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link class="nav-link" data-widget="pushmenu" to="#" role="button"><i class="fas fa-bars"></i></router-link>
          </li>
          <li class="nav-item d-none d-sm-inline-block">
            <router-link to="/" class="nav-link">Home</router-link>
          </li>
          <li class="nav-item d-none d-sm-inline-block">
            <router-link to="#" class="nav-link">Contact</router-link>
          </li>
        </ul>

        <!-- SEARCH FORM -->
        <form class="form-inline ml-3">
          <div class="input-group input-group-sm">
            <input class="form-control form-control-navbar" type="search" placeholder="Search" aria-label="Search">
            <div class="input-group-append">
              <button class="btn btn-navbar" type="submit">
                <i class="fas fa-search"></i>
              </button>
            </div>
          </div>
        </form>

        <!-- Right navbar links -->
        <ul class="navbar-nav ml-auto">
          <!-- Messages Dropdown Menu -->

          <!-- Notifications Dropdown Menu -->

          <li class="nav-item dropdown">
            <router-link class="nav-link" data-toggle="dropdown" to="#">
                <i><div class="media">
                 <i class ="fa fa-user"></i>
                </div></i>
              <!-- <i class="far fa-user fa-2x"></i> -->
              <!-- <span class="badge badge-danger navbar-badge">3</span> -->
            </router-link>
            <div class="dropdown-menu dropdown-menu-lg dropdown-menu-right">
              <router-link to="#" class="dropdown-item">
                <!-- Message Start -->
                <div class="media">
                  <div class="media-body">
                    <h3 class="dropdown-item-title text-center">
                      <router-link to="/profile" class="text-center">Profile</router-link>
                    </h3>
                </div>
                </div>
                <!-- Message End -->
              </router-link>
              <div class="dropdown-divider"></div>
              <router-link to="#" class="dropdown-item">
                <!-- Message Start -->
                <div class="media">
                  <div class="media-body">
                    <h3 class="dropdown-item-title text-center">
                      <p @click.prevent="logout" class="text-center">Logout</p>
                    </h3>
                </div>
                </div>
                <!-- Message End -->
              </router-link>
              </div>
          </li>

        </ul>
      </nav>
      <!-- /.navbar -->

      <!-- Main Sidebar Container -->
      <aside class="main-sidebar sidebar-dark-primary elevation-4">
        <!-- Brand Logo -->
        <router-link to="/" class="brand-link">
          
          <span class="brand-text font-weight-light">Auroville Foodlink</span>
        </router-link>

        <!-- Sidebar -->
        <div class="sidebar">
          <!-- Sidebar Menu -->
          <nav class="mt-2">
            <ul class="nav nav-pills nav-sidebar flex-column" data-widget="treeview" role="menu" data-accordion="false">
              <!-- Add icons to the links using the .nav-icon class
                   with font-awesome or any other icon font library -->
              <li class="nav-item menu-open">
                <router-link to="/" class="nav-link active">
                  <i class="nav-icon fas fa-tachometer-alt"></i>
                  <p>
                    Dashboard
                    <!-- <i class="right fas fa-angle-left"></i> -->
                  </p>
                </router-link>

              </li>
              <li class="nav-item">
                <router-link to="/new-orders" class="nav-link">
                  <i class="nav-icon fas  fa-cart-arrow-down"></i>
                  <p>
                 Create Order
                    <!-- <span class="right badge badge-danger">New</span> -->
                  </p>
                </router-link>
              </li>
              <li class="nav-item">
                <router-link to="/my-orders" class="nav-link">
                  <i class="nav-icon fas fa-file-invoice"></i>
                  <p>
                    My Orders
                    <!-- <span class="right badge badge-danger">New</span> -->
                  </p>
                </router-link>
              </li>

           </ul>
          </nav>
          <!-- /.sidebar-menu -->
        </div>
        <!-- /.sidebar -->
      </aside>

      <!-- Content Wrapper. Contains page content -->

</template>

<script>
    export default {
        'name': 'Header',
        data(){
            return {
                user: {
                    full_name: ''
                },
                user_image: '/static/dist/img/user2-160x160.jpg'
            }
        },
        methods: {
            logout(e){
                Swal.fire({
                  title: 'Are you sure?',
                  text: "You will be logged out!",
                  icon: 'warning',
                  showCancelButton: true,
                  confirmButtonColor: '#3085d6',
                  cancelButtonColor: '#d33',
                  confirmButtonText: 'Yes!'
                }).then((result) => {
                  if (result.isConfirmed) {
                    // logout
                    this.$session.clear();
                    localStorage.clear();
                    Swal.fire(
                      'Logged Out!',
                      'You have been logged out.',
                      'success'
                    )
                    setTimeout(function () {
                        window.location.href = '/login';
                    }, 2000);
                  }
                })
            }
        },
        mounted(){
            // if(this.)
            if(!['/login', '/register', '/signup'].includes(this.$route.path)){
                this.user = this.$sessionUserData();
            }
            // console.log(this.user.full_name)
        },
        computed: {
            // profileImage: {
            //
            // }
        },
        watch: {
            'user.user_image': {
                handler(user_image){
                    // alert(user_image);
                    this.user_image = this.$remoteUrl+user_image;
                },
                deep: true
            }
        }
    }
</script>
