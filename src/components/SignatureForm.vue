<template>
  <form class="signature-form">
    <h4>{{ title }}</h4>
    <InputGroup
      v-model="signatureName"
      inputType="text"
      inputName="name"
      inputPlaceholder="Name"
    />
    <InputGroup
      v-model="signaturePosition"
      inputType="text"
      inputName="position"
      inputPlaceholder="Position"
    />
    <InputGroup
      v-model="signaturePhone"
      inputType="text"
      inputName="phone"
      inputPlaceholder="Phone number"
    />
    <InputGroup
      v-model="signatureMobile"
      inputType="text"
      inputName="mobile"
      inputPlaceholder="Mobile number"
    />
    <Button Text="AOG Signature" />
    <Button Text="AOW Signature" />
  </form>
</template>
<script>
import InputGroup from "./InputGroup.vue";
import Button from "./Button.vue";
export default {
  name: "SignatureForm",
  props: {
    title: String,
  },
  components: {
    InputGroup,
    Button,
  },
};
</script>

<style scoped>
.signature-form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
</style>
