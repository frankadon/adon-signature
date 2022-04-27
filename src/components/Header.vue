<template>
  <nav
    class="navbar navbar-expand-lg navbar-dark"
    style="background-color: #000000"
  >
    <div class="container">
      <a class="navbar-brand" href="/">ADON PAGES</a>
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
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <a class="nav-link" aria-current="page" href="/">Ad On Signature</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="/qr-generator">QR Generator</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="/about">About</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Navigation",
};
</script>

<style>
.content {
  width: 80%;
  margin: auto;
}
#nav {
  height: 80px;
  background-color: var(--black);
  margin-bottom: 10px;
  display: flex;
}

#nav a {
  font-weight: 500;
  color: var(--primary);
  text-decoration: none;
}

#nav a.router-link-exact-active {
  color: var(--light);
}
</style>