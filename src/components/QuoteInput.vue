<template>
  <div class="row">
    <div class="col-md-8 col-centered">
      <label for="quote">Quote</label>
      <textarea class="form-control" rows="4" cols="5" v-model="quoteInput"></textarea>
    </div>
    <div class="col-md-12 text-center" style="margin-top:15px;margin-bottom:15px;">
      <button type="button" class="btn btn-primary" style="text-align: center;" @click="addQuote">
        <b>Add Quote</b>
      </button>
    </div>
  </div>
</template>
<script>
import { busEvent } from "../main";

export default {
  data: function() {
    return {
      quoteInput: ""
    };
  },
  methods: {
    addQuote() {
      busEvent.$emit("newQuoteAdded", this.quoteInput);
      this.quoteInput = "";
    }
  }
};
</script>
<style scoped>
.col-centered {
  margin: 0 auto;
  float: none;
}
</style>