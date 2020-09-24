<template>
  <div class="h-100">
    <div id="content">
      <Navbar />

      <Nuxt />

      <div id="footer-push"></div>
    </div>

    <Footer />
  </div>
</template>

<script lang="ts">
import Vue from "vue";

import Navbar from "@/components/Navbar.vue";
import Footer from "@/components/Footer.vue";

export default Vue.extend({
  components: {
    Navbar,
    Footer
  }
});
</script>

<style>
#__layout {
  width: 100%;
  height: 100%;
}

#content {
  min-height: 100%;
  margin-bottom: -56px;
  overflow-x: hidden;
}

#footer-push {
  height: 56px;
}

#footer {
  height: 56px;
}
</style>
