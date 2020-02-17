<template>
  <div class="row">
    <div class="col-xs-12">
      <app-quote v-for="(quote, index) in quotes" :key="index" :quote="quote"></app-quote>
    </div>
  </div>
</template>
<script>
import Quote from "./Quote.vue";
import { busEvent } from "../main";
export default {
  data: function() {
    return {
      quotes: []
    };
  },
  components: {
    appQuote: Quote
  },
  created() {
    busEvent.$on("newQuoteAdded", quote => {
      this.quotes.push(quote);
    });
  }
};
</script>