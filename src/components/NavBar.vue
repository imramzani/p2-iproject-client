<template>
  <header>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
      <div class="container px-5">
        <!-- <a class="navbar-brand text-warning" href="#!"
          ><strong>Resvue</strong></a
        > -->

        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <router-link
                class="navbar-brand text-warning nav-link active"
                to="/"
                ><strong>Supreme Soccer</strong></router-link
              >
            </li>
            <li v-if="isLogin == false" class="nav-item">
              <router-link class="nav-link active" to="/register"
                >Register</router-link
              >
            </li>
            <li v-if="isLogin == false" class="nav-item">
              <router-link class="nav-link active" to="/login"
                >Login</router-link
              >
            </li>
            <li v-if="isLogin == true" class="nav-item">
              <router-link class="nav-link active" to="/landing"
                >My Favorite</router-link
              >
            </li>
            <li v-if="isLogin == true" class="nav-item">
              <a @click.prevent="logout" class="nav-link active btn">Log Out</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </header>
</template>

<script>
import swal from "sweetalert";
export default {
  name: "NavBar",
  computed: {
    isLogin() {
      return this.$store.state.isLogin;
    },
  },
  methods: {
    logout() {
      localStorage.clear();
      this.$store.commit("SET_ISLOGIN", false);
      this.$store.commit("SET_FAV", "");
      this.$store.commit("SET_CURRENTUSER", "");
      swal("Why are you leaving?", "Come back again, okay..", "success");
      this.$router.push("/login");
    },
  },
};
</script>

<style></style>
