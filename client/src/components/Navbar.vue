<template>
  <div class="fixed-top mb-5">
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarTogglerDemo01" aria-controls="navbarTogglerDemo01" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse mr-5" id="navbarTogglerDemo01">
        <a class="navbar-brand" href="#">E-Commerce</a>
        <ul class="navbar-nav mr-auto mt-2 mt-lg-0">
          <li class="nav-item">
            <a class="nav-link" href="#">Home</a>
          </li>
          <li class="nav-item">
            <a @click.prevent="addProduct" class="nav-link" href="#">Add Product</a>
          </li>
        </ul>
        <div class="mr-2">
          <i @click.prevent="logout" class="logout material-icons my-2 my-sm-0" type="submit">power_settings_new</i>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
import swal from 'sweetalert2'
export default {
  name: 'Navbar',
  data () {
    return {
      isHome: false
    }
  },
  methods: {
    logout () {
      swal.fire({
        title: 'Wait!',
        text: 'Are you sure want to logout',
        icon: 'warning',
        showCancelButton: true,
        confirmButtonColor: '#45aaf2',
        cancelButtonColor: '#e84118',
        confirmButtonText: 'Yes, i want'
      })
        .then((result) => {
          if (result.isConfirmed) {
            localStorage.clear()
            this.$router.push('/login')
          }
        })
    },

    addProduct () {
      this.$router.push('/Add')
    }
  },
  computed: {
  }
}
</script>

<style>
  .logout {
    color: #a4b0be;
    background-origin: red;
    border: 0px;
  }
  .logout:hover{
    color: #CAD3C8;
  }
</style>
