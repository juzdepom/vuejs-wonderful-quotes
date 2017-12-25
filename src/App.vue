<template>
    <div class="container">
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
        }
    }
</script>

<style>
</style>
