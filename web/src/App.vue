<template>
  <div>
    <NavBar />
    <router-view></router-view>
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue'
import "bootstrap/dist/css/bootstrap.min.css"
import "bootstrap/dist/js/bootstrap"
import $ from 'jquery'

export default {
  components: {
    NavBar
  },
  setup() {
    $.ajax({
      url: "http://127.0.0.1:3000/user/account/token/",
      type: "post",
      data: {
        username: "jlx",
        password: "123",
      },
      success(resp) {
        console.log(resp);
      },
      error(resp) {
        console.log(resp);
      }
    });

    $.ajax({
      url: "http://127.0.0.1:3000/user/account/info/",
      type: "get",
      headers: {
        Authorization: "Bearer " + "eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiI3ZDNhMDY3ZjI5NmI0ZmQ4OTlhNWYyMmVjMmVlNTUyOSIsInN1YiI6IjEiLCJpc3MiOiJzZyIsImlhdCI6MTcwOTY4MjA5MiwiZXhwIjoxNzEwODkxNjkyfQ.I9mYWvaRf2xIhABQ8Pg6qRxFwXIO-2z_vWTrjWqWP14",
      },
      success(resp) {
        console.log(resp);
      },
      error(resp) {
        console.log(resp);
      }
    });

    $.ajax({
      url: "http://127.0.0.1:3000/user/account/register/",
      type: "post",
      data: {
        username: "ls",
        password: "789",
        confirmedPassword: "789",
      },
      success(resp) {
          console.log(resp);
        },
        error(resp) {
          console.log(resp);
        },
    });
  },
}
</script>

<style>
body {
  background-image: url("./assets/images/background.png");
  background-size: cover;
}
</style>
