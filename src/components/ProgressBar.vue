<template>
  <div class="row">
    <div class="col-md-12">
      <div class="progress">
        <div
          class="progress-bar text-center"
          role="progressbar"
          aria-valuenow="70"
          aria-valuemin="0"
          aria-valuemax="100"
          :style="{width: (totalQuotes*10) + '%'}"
        >
          <span style="font-size:16px">
            <b>{{ totalQuotes }} / 10</b>
          </span>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { busEvent } from "../main";
export default {
  data: function() {
    return {
      totalQuotes: 0
    };
  },
  created() {
    busEvent.$on("newQuoteAdded", quote => {
      if (this.totalQuotes <= 9) {
        this.totalQuotes++;
      }
    });
    busEvent.$on("deleteQuote", quote => {
      this.totalQuotes--;
    });
  }
};
</script>