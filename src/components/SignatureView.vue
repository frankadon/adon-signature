<template>
  <div>
    <h4>{{ title }}</h4>
    <br />
  </div>
  <div class="signature-data">
    <div class="data">
      <div class="logo">
        <img src="../assets/AOG-logo.png" alt="logo" />
      </div>
      <div class="info">
        <strong> {{ name }} </strong>
        <p>{{ position }}</p>
        <p class="links">
          <a href=""
            ><img src="../assets/icons/icon-01.png" alt="" /> {{ phone }}
          </a>
          <br />
          <a href=""
            ><img src="../assets/icons/icon-02.png" alt="" />
            www.adongroup.com.au</a
          >
        </p>
      </div>
      <div class="partner">
        <img src="../assets/AOG-animated-logos.gif" alt="partners" />
      </div>
    </div>
    <div class="disclaimer">
      <p>
        This email, its contents and any attachments are strictly confidential.
        They must not be used, distributed, copied or read by any person other
        than the addressee. Unauthorised use, disclosure, copying or reliance on
        the contents of and attachments to this email by anyone other than the
        addressee may be unlawful. If you have received this email and
        attachments in error please contact us at Ad on Group immediately to
        facilitate its return.
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "SignatureView",
  props: {
    title: String,
  },
};
</script>

<style scope>
.signature-data {
  background-color: var(--dark);
  border-radius: 0.5rem;
  padding: 10px;
  width: 600px;
  height: auto;
}
.data {
  display: flex;
  flex-direction: row;
  gap: 1.5rem;
}
.logo {
  width: 30%;
}
.logo img {
  width: 100%;
}
.info {
  width: 30%;
  color: var(--white);
}
.info .links {
  font-size: 0.7rem;
  margin-top: 10px;
}
.info p a img {
  width: 0.5rem;
}
.info p a {
  text-decoration: none;
  color: var(--white);
}
.partner {
  width: 40%;
}
.partner img {
  width: 100%;
}
.disclaimer {
  color: var(--white);
}
.disclaimer p {
  font-size: 0.5rem;
  line-height: 1.2;
}
</style>