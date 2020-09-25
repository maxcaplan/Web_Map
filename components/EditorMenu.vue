<template>
  <div>
    <form @submit.prevent="convert">
      <h5>
        Location:
        <a
          v-show="popoverActive"
          tabindex="0"
          href="#"
          class="badge bg-light text-dark text-decoration-none"
          role="button"
          data-container="body"
          data-toggle="popover"
          data-trigger="focus"
          data-placement="bottom"
          title="Signed Degrees"
          :data-content="popoverHTML"
          >Signed Degrees <span class="text-danger">*</span></a
        >

        <a
          v-show="!popoverActive"
          tabindex="0"
          href="https://en.wikipedia.org/wiki/Decimal_degrees"
          target="_blank"
          class="badge bg-light text-dark text-decoration-none"
          role="button"
          >Signed Degrees <span class="text-danger">*</span></a
        >
      </h5>

      <div class="row">
        <div class="col-12 col-md mb-2 mb-md-0">
          <div class="form-group">
            <label for="lat">Latitude</label>
            <input
              type="number"
              name="lat"
              class="form-control"
              v-model="lat"
            />
          </div>
        </div>

        <div class="col-12 col-md">
          <div class="form-group">
            <label for="long">Longitude</label>
            <input
              type="number"
              name="long"
              class="form-control"
              v-model="long"
            />
          </div>
        </div>
      </div>
    </form>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "EditorMenu",

  data() {
    var lat: any;
    var long: any;

    // Popover data
    const popoverHTML: string = `
    Express Latitude and Longitude degrees as a decimal.
    Also known as Decimal Degrees (DD).
    <a href="https://en.wikipedia.org/wiki/Decimal_degrees" target="_blank">Learn More<a/>
    `;
    var popoverActive: boolean = false;

    return {
      lat,
      long,
      popoverHTML,
      popoverActive
    };
  },

  mounted() {
    // Enable popovers on client
    if (process.client) {
      const bootstrap = require("bootstrap/dist/js/bootstrap.esm.js");

      var popoverTriggerList: Element[] = [].slice.call(
        document.querySelectorAll('[data-toggle="popover"]')
      );

      if (popoverTriggerList && popoverTriggerList.length > 0) {
        var popoverList = popoverTriggerList.map(function(popoverTriggerEl) {
          return new bootstrap.Popover(popoverTriggerEl, { html: true });
        });

        this.popoverActive = true;
      }
    }
  }
});
</script>

<style scoped lang="scss"></style>
