<template>
  <div class="container">
    <app-title></app-title>
    <app-progress-bar></app-progress-bar>
    <app-quote-inpute></app-quote-inpute>
    <app-quotes-display></app-quotes-display>
    <app-info-alert></app-info-alert>
  </div>
</template>

<script>
import ProgressBar from "./components/ProgressBar.vue";
import Title from "./components/Title.vue";
import QuoteInput from "./components/QuoteInput.vue";
import QuoteDisplay from "./components/QuoteDisplay.vue";
import appInfoAlert from "./components/InfoAlert.vue";
export default {
  components: {
    appProgressBar: ProgressBar,
    appTitle: Title,
    appQuoteInpute: QuoteInput,
    appQuotesDisplay: QuoteDisplay,
    appInfoAlert: appInfoAlert
  }
};
</script>

<style>
</style>
