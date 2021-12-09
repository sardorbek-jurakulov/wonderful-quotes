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
    data() {
      return {
        hasBeenAddedQuote: '',
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
