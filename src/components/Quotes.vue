<template>
  <div class="quotes-container">
    <div 
      v-for="(quote, index) in quotesList" 
      :key="index" 
      class="quote-card" 
      @click="removeQuote(index, $event)">
        {{ quote }}
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
      quotesList: [],
      quotesCount: 0,
    }
  },
  watch: {
    hasBeenAddedQuote() {
      this.pushNewQuoteToQuotesList(this.hasBeenAddedQuote);
    },
    quotesList() {
      this.quotesCount = this.quotesList.length;
      if((this.quotesCount == 10) || (this.quotesCount > 10)) {
        this.$emit('isQuotesCountOwerflow', true);
      } else {
        this.$emit('isQuotesCountOwerflow', false);
      }
      this.$emit('quotesCountWasChanged', this.quotesCount);
    }
  },
  methods: {
    pushNewQuoteToQuotesList(newQuote) {
      this.quotesList.push(newQuote);
    },
    removeQuote(indexQuote, evt) {
      this.quotesList.splice(indexQuote, 1);
    },
  }
}
</script>

<style>
.quotes-container {
  margin-top: 30px;
  margin-bottom: 30px;
}

.quote-card {
  display: flex;
  align-items: center;
  justify-content: center;
  border: 1px solid #222;
  border-radius: 5px;
  margin-bottom: 30px;
  padding-left: 10px; 
  padding-top: 5px; 
  padding-right: 10px; 
  padding-bottom: 5px; 
  background-color: #eee;
  color: #222;
}
</style>