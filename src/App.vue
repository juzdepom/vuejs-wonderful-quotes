<template>
    <div class="container">
      <new-quote></new-quote>
      <quote-grid :quotes="quotes"></quote-grid>
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
        components: {
          QuoteGrid,
          NewQuote,
        }
    }
</script>

<style>
</style>
