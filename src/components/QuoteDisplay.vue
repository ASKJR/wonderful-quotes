<template>
  <div class="row">
    <div class="col-xs-12">
      <app-quote v-for="x in 10" :key="x"></app-quote>
    </div>
  </div>
</template>
<script>
import Quote from "./Quote.vue";
export default {
  components: {
    appQuote: Quote
  }
};
</script>