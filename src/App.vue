<template>
  <div class="container">
    <app-quote-progress :quotesQuantity="quotes.length" :maxquotes="maxquotes"></app-quote-progress>
    <app-quote-new @addedNewQuote="quoteAdded" :quotesQuantity="quotes.length"></app-quote-new>
    <app-quotes :quotes="quotes" @removeThisQuote="removeQuote"></app-quotes>
    <div class="hint">Hint: click onto the Quote to delete it!</div>
  </div>
</template>

<script>
import QuotesList from "./components/QuotesList.vue";
import QuoteNew from "./components/QuoteNew.vue";
import QuoteProgress from "./components/QuoteProgress.vue";

export default {
  data: function() {
    return {
      quotes: [],
      maxquotes: 9
    };
  },
  components: {
    appQuotes: QuotesList,
    appQuoteNew: QuoteNew,
    appQuoteProgress: QuoteProgress
  },
  methods: {
    quoteAdded(quote) {
      this.quotes.push(quote);
    },
    removeQuote(index) {
      this.quotes.splice(index, 1);
    }
  }
};
</script>

<style>
body {
  background-color: rgb(122, 101, 243);
}
.container {
  max-width: 1230px;
  margin: 0 auto;
  padding: 0 10px;
}
.hint {
  background-color: cadetblue;
  box-sizing: border-box;
  width: 100%;
  margin: 25px auto;
  text-align: center;
  padding: 15px;
  border-radius: 10px;
  font-size: 24px;
  line-height: 28px;
  cursor: grab;
}
</style>
