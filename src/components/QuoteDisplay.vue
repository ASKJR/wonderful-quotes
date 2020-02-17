<template>
  <div class="row">
    <div class="col-xs-12">
      <app-quote v-for="(quote, index) in quotes" :key="index" :quote="quote" :index="index"></app-quote>
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
      if (this.quotes.length <= 9) {
        this.quotes.push(quote);
      } else {
        alert("Too many Quotes! Delete some before adding new ones!");
      }
    });
    busEvent.$on("deleteQuote", id => {
      this.quotes.splice(id, 1);
    });
  }
};
</script>