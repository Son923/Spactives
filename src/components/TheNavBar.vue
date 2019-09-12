//TODO Web Template Studio: Add a new link in the NavBar for your page here.
// A skip link is included as an accesibility best practice. For more information visit https://www.w3.org/WAI/WCAG21/Techniques/general/G1.
<template>
  <b-container fluid>
    <div class="skipLink">
      <a href="#mainContent">Skip to Main Content</a>
    </div>
    <b-nav class="navbar navbar-expand-sm navbar-light justify-content-between">
      <a class="navbar-brand" href="/">
        <img src="@/assets/logo.png" alt="">
      </a>
      <div class="navbar-nav">
        <b-nav-item class="nav-item nav-link active" to="/Blank">Manu</b-nav-item>
        <b-nav-item class="nav-item nav-link active" to="/Grid">Grid</b-nav-item>
        <b-nav-item class="nav-item nav-link active" to="/Blank2">Blank2</b-nav-item>
        <b-nav-item class="nav-item nav-link active" to="/List">List</b-nav-item>
        <b-nav-item class="nav-item nav-link active" to="/Master_Detail">Master_Detail</b-nav-item>
      </div>
      <div>
        <a class="navbar-brand" href="/">
          <img src="@/assets/svg/Mail.svg" alt="">
        </a>
        <a class="navbar-brand" href="/">
          <img class="avatar" src="@/assets/image.png" alt="">
        </a>
        <a class="navbar-brand" href="/">
          <p>Duong <i><img src="@/assets/svg/ArrowDown.svg" alt=""></i></p>
        </a>
      </div>
    </b-nav>
  </b-container>
</template>

<script>
export default {
  name: "TheNavBar"
};
</script>

<style scoped>
.skipLink a {
  position: absolute;
  left: -100px;
  top: -100px;
}

.skipLink a:focus {
  position: fixed;
  z-index: 1000;
  top: 0;
  left: 0;
  padding: 10px;
  color: #ffffff;
  background: #000000;
}
.avatar {
  border-radius: 50%;
}
</style>
