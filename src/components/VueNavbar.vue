<template >
  <nav class="navbar navbar-expand-lg" 
       :class="changeNavBarTheme">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">Navbar</a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarNav"
        aria-controls="navbarNav"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="#">Home</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Features</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Pricing</a>
          </li>
          <li class="nav-item">
            <button
              @click.prevent="lightTheme = !lightTheme"
              class="btn btn-success"
            >
              Toggle theme
            </button>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>


<script>
import { ref } from 'vue';
export default {
    computed: {
        changeNavBarTheme() {
            return {
                'navbar-light': !this.lightTheme,
                'bg-light': !this.lightTheme,
                'navbar-dark': this.lightTheme,
                'bg-dark': this.lightTheme
            }
        }
    },
     setup() {

    return {
      lightTheme: ref(false)
    };
  }
};
</script>



<style scoped>
.darkTheme {
  background: black;
  color: white;
}
</style>