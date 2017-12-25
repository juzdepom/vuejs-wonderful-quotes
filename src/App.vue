<template>
    <div class="container">
      <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
      <new-quote @quoteAdded="newQuote"></new-quote>
      <br />
      <quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></quote-grid>
      <div class='row'>
        <div class='col-sm-12 text center'>
          <div class='alert alert-info'>
            Info: Click on a Quote to delete it!
          </div>
        </div>
      </div>
    </div>
</template>

<script>
    import Header from './components/Header.vue'
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';

    export default {
        data: function(){
          return {
            quotes: [
              'This is my default quote.',
              'This is another quote.'
            ],
            maxQuotes: 10,
          }
        },
        methods: {
          newQuote(quote){
            if(this.quotes.length >= this.maxQuotes){
              alert("You've reached a max limit of 10 quotes. Please delete a quote.")
            }
            if(quote != ''){
              this.quotes.push(quote)
            }
          },
          deleteQuote(index){
            this.quotes.splice(index, 1);
          }
        },
        components: {
          QuoteGrid,
          NewQuote,
          appHeader: Header
        }
    }
</script>

<style>
</style>
