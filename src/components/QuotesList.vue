<template>
  <div class="quote-list">
    <app-quote-single 
    v-for="(quote, index) in quotes" 
    :key="index"
    @click.native="deleteQuote(index)"
    >{{ quote }}</app-quote-single>
  </div>
</template>

<script>
import QuoteSingle from "./QuoteSingle.vue";
export default {
  props: ["quotes"],
  components: {
    appQuoteSingle: QuoteSingle
  },
methods: {
  deleteQuote(index) {
    this.$emit('removeThisQuote', index);
  }
}
};
</script>

<style>
.quote-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
</style>