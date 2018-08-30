<template>
  <div class="container">
    <app-header
      :quoteCount="quotes.length"
      :maxQuotes="maxQuotes"
    ></app-header>
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
        'Не волнуйтесь, если что-то не работает. Если бы всё работало, вас бы уволили.',
        'Измерять продуктивность программиста подсчетом строк кода — это так же, как оценивать постройку самолета по его весу.',
        'Многие из вас знакомы с достоинствами программиста. Их всего три, и разумеется это: лень, нетерпеливость и гордыня.',
        'Большинство хороших программистов делают свою работу не потому, что ожидают оплаты или признания, а потому что получают удовольствие от программирования.'
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
        if (this.quotes.length >= this.maxQuotes) {
          return alert('Сначало, удалите цитату!');
        }

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
