<template>
    <div class="container">
      <app-new-quote @createdNewQuote="hasBeenAddedQuote = $event"></app-new-quote>
      <app-quotes :hasBeenAddedQuote="hasBeenAddedQuote"></app-quotes>
    </div>
</template>

<script>
import NewQuote from './components/NewQuote.vue';
import Quotes from './components/Quotes.vue';
  export default {
    data: {
      hasBeenAddedQuote: '',
    },
    watch: {
      hasBeenAddedQuote() {
        console.log(this.hasBeenAddedQuote);
      }
    },
    components: {
      appNewQuote: NewQuote,
      appQuotes: Quotes,
    }
  }
</script>

<style>
</style>
