<template>
  <!-- <div class="container"> -->
  <Header />
  <div class="container mt-3">
    <router-view />
  </div>
  <Footer />
  <!-- </div> -->
</template>
<script>
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
export default {
  components: {
    Header,
    Footer,
  },
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");
:root {
  --primary: #5360ea;
  --accent: #ff46d7;
  --hover: #b5bbf9;
  --light: #f1f2ff;
  --white: white;
  --dark: #252525;
  --black: #000000;
  --fonts: "Montserrat";
  --corner-radius: 0.5rem;
  --shadow: 0 10px 100px rgba(0, 0, 0, 0.15);
}
/* * {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
.container {
  width: 100%;
  margin: auto;
} */
.content {
  width: 80%;
  margin: auto;
}
#app {
  font-family: var(--fonts);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: var(--dark);
}
.center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>
