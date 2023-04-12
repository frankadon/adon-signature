<template>
  <footer>
    <div class="container">
      Copyrights {{ yearToday }}
      <a href="">AdonPages</a>
      all rights reserved.
    </div>
  </footer>
</template>

<script>
const date = new Date();
const year = date.getFullYear();
export default {
  name: "Footer",
  data() {
    return {
      yearToday: year,
    }
  },
};
</script>

<style scope>
footer {
  /* margin-top: 20rem; */
  background-color: var(--black);
  padding: 1rem 0 1rem 0;
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  color: var(--white);
}
a {
  text-decoration: none;
  color: var(--primary);
}
</style>