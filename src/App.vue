<template>
    <div class="container">
      <app-quote-count-in-progress :quotesCount="quotesCount"></app-quote-count-in-progress>
      <app-new-quote @createdNewQuote="hasBeenAddedQuote = $event"></app-new-quote>
      <app-quotes :hasBeenAddedQuote="hasBeenAddedQuote" @quotesCountWasChanged="quotesCount = $event"></app-quotes>
    </div>
</template>

<script>
import NewQuote from './components/NewQuote.vue';
import Quotes from './components/Quotes.vue';
import QuoteCountInProgress from './components/QuoteCountInProgress.vue';
  export default {
    data() {
      return {
        hasBeenAddedQuote: '',
        quotesCount: 0,
      }
    },
    components: {
      appNewQuote: NewQuote,
      appQuotes: Quotes,
      appQuoteCountInProgress: QuoteCountInProgress,
    }
  }
</script>

<style>
</style>
