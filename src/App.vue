<template>
  <div class="container">
    <app-header></app-header>
    <app-new-quote
      @quoteAdded="newQuote"
    ></app-new-quote>
    <app-quote-grid
      :quotes="quotes"
      @quoteDeleted="deleteQuote"
    ></app-quote-grid>
    <div class="row" v-if="!!quotes">
      <div class="col-sm-12 text-center mt-5">
        <div class="alert alert-info">Кликните на цитату, чтобы удалить!</div>
      </div>
    </div>
  </div>
</template>

<script>
  import QuoteGrid from './components/QuoteGrid';
  import NewQuote from './components/NewQuote';
  import Header from './components/Header';

  export default {
  data() {
    return {
      quotes: [
        'Первая цитата',
        'Вторая цитата'
      ],
      maxQuotes: 10
    }
  },
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote,
    appHeader: Header
  },
  methods: {
    newQuote (quote) {
      if (!!quote) {
        this.quotes.push(quote);
      }
    },
    deleteQuote (index) {
      this.quotes.splice(index, 1);
    }
  }
}
</script>

<style>

</style>
