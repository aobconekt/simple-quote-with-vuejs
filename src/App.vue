<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <app-new-quote @quoteAdded="createdQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes" @quoteDeleted="deletedQuote"></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a quote to deleted it!</div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';
import Header from './components/Header.vue';
export default {
  data: function(){
    return {
      quotes: [],
      maxQuotes: 10
    }
  },
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote,
    appHeader: Header
  },
  methods: {
    createdQuote(quote){
      if(this.quotes.length > this.maxQuotes){
        return alert("Please delete some quotes before adding new!");
      }
      this.quotes.push(quote);
    },
    deletedQuote(index){
      this.quotes.splice(index, 1);
    }
  }
}
</script>

<style lang="scss">

</style>
