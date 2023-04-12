<template>
    <div :class=clsname>
        <img :src=logolink alt="">
        <strong>{{ text }}</strong>
    </div>
</template>

<script>
    export default {
        name: "Signature Logo",
        props: {
            text: String,
            logolink: String,
            clsname: String,
        },
    }
</script>

<style scope>
.logo-aog {
  width: 30%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: start;
  color: #ffffff;
  gap: .5rem;
}
.logo-aow {
  width: 30%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: start;
  color: #ffffff;
  gap: .5rem;
}
.logo-aog img {
  width: 100%;
}
.logo-aow img {
  width: 100%;
  margin-top: -3rem;
}

.logo-aow strong {
  font-size: 12px;
}

.logo-aog strong {
  font-size: 12px;
}
.logo-aogaow img {
    width: 100%;
}
</style>