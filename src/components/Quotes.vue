<template>
  <div>
    <div v-for="(quote, index) in quotesList" :key="index">
      <p>
        <i>quote</i>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    hasBeenAddedQuote: {
      type: [String, Number],
      required: false,
    }
  },
  data() {
    return {
      quotesList: []
    }
  },
  watch: {
    hasBeenAddedQuote() {
      this.pushNewQuoteToQuotesList(this.hasBeenAddedQuote);
    }
  },
  methods: {
    pushNewQuoteToQuotesList(newQuote) {
      this.quotesList.push(newQuote);
    }
  }
}
</script>

<style>

</style>