<template>
  <footer class="footer-wrapper">
    <div class="footer-content">
      <p class="footer-text">License MIT</p>
      <p class="footer-text">Author: deneuv34</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: "FooterComponent"
};
</script>

<style>
.footer-wrapper {
  position: fixed;
  bottom: 0;
  background-color: aliceblue;
  width: 100vw;
}
p.footer-text {
  font-weight: bold;
  font-family: "Courier New", Courier, monospace;
}
.footer-content {
  text-align: center;
  padding-top: 50px;
  padding-bottom: 50px;
}

@media (max-width: 767px) {
  .footer-wrapper {
    position: relative;
    bottom: unset;
  }
}
</style>