<template>
  <nav class="navbar navbar-dark bg-primary">
    <div class="container-fluid">
      <nuxt-link to="/" class="navbar-brand font-monospace font-weight-bold m-0"
        ><i class="fas fa-layer-group"></i> Web_Map
      </nuxt-link>
    </div>
  </nav>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  name: "Navbar"
});
</script>
