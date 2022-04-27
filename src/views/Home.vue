<template>
  <div class="row">
    <div class="all-content">
      <div class="text-content">
        <h1>Adon Pages</h1>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloribus
          ipsam voluptates fuga est optio, aliquam reiciendis sunt blanditiis
          eius, totam consequatur repudiandae odit. Delectus quaerat id dolorem
          suscipit accusamus quod.
        </p>
        <div class="action-btn">
          <Button Text="Make Your Signature Now" bgColor="primary" />
        </div>
      </div>
      <div class="image-content">
        <img src="" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
import Button from "../components/Button.vue";
export default {
  name: "Home",
  components: {
    Button,
  },
};
</script>
<style scoped>
.all-content {
  display: flex;
  flex-direction: row;
  gap: 20px;
}
.text-content {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}
.text-content p {
  width: 100%;
}
.action-btn {
  width: 100%;
}
.image-content {
  background-color: var(--dark);
  width: 100%;
  height: auto;
  background-color: var(--white);
  box-shadow: var(--shadow);
  border-radius: var(--corner-radius);
}
</style>
