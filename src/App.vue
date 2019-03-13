<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <NewQuote @quoteAdded="addNewQuote"></NewQuote>
    <quotegrid :quotes="quotes" @quoteDeleted="deleteQuote"></quotegrid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a Quote to delete it</div>
      </div>
    </div>
  </div>
</template>

<script>
import Quotegrid from "./components/Quotegrid.vue";
import NewQuote from './components/NewQuote.vue';
import Header from './components/Header.vue';

export default {
  data() {
    return {
      quotes: [
        "Just a quote to see something",
        ],
        maxQuotes: 10,
    };
  },
  methods:{
    addNewQuote(quote){
      if(this.quotes.length < this.maxQuotes){
        this.quotes.push(quote);
      }
      else{
        return alert('Please delete quotes first!');
      }
      
    },
    deleteQuote(index){
      this.quotes.splice(index, 1);
    },
  },
  components: {
    Quotegrid,
    NewQuote,
    appHeader: Header,
  }
};
</script>

<style>
</style>
