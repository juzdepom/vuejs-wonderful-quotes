<template>
  <div class="row"
  style="padding: 20px"
  >
    <form>
      <div class="col-sm-8.col-sm-offset-2.col-xs-12.col-md-6.col-md-offset-3">
        <label>Quote</label>
        <textarea class="form-control" rows="3" v-model="quote"></textarea>
      </div>
      <div style="margin-top: 10px" class="col-sm-8.col-sm-offset-2.col-xs-12.col-md-6.col-md-offset-3">
        <button type="button" class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
      </div>
    </form>
  </div>
</template>

<script>
  import Quote from './Quote.vue'
 export default {
   data: function (){
     return {
       quote: ''
     }
   },
   methods: {
     createNew(){
       this.$emit('quoteAdded', this.quote);
       this.quote = '';
     }
   }
 }
</script>

<style scoped>

</style>
