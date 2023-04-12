<template>
    <a :href=href>
        <img :src=link alt=""> {{ text }}
    </a>
</template>

<script>
export default {
  name: "Signature Link",
  props: {
    text: String,
    link: String,
    href: String,
  },
};
</script>

<style scope>
a {
  text-decoration: none;
  color: #ffffff;
}
img {
  width: 0.5rem;
}
</style>