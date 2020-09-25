<template>
  <div class="container py-3">
    <h1>Home</h1>

    <div class="card card-body">
      <editor-menu />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

import EditorMenu from "@/components/EditorMenu.vue";

export default Vue.extend({
  name: "Index",

  components: {
    EditorMenu
  }
});
</script>

<style></style>
