<template>
  <div class="quotes-container">
    <div @click="removeQuote" style="cursor:pointer;" v-for="(quote, index) in quotesList" :key="index">
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
      this.quotesCount = this.pushNewQuoteToQuotesList(this.hasBeenAddedQuote);
      this.$emit('quotesCountWasChanged', this.quotesCount);
    }
  },
  methods: {
    pushNewQuoteToQuotesList(newQuote) {
      return this.quotesList.push(newQuote);
    },
    removeQuote(evt) {
      let isBeingDelatedQuote = evt.target.innerHTML.trim();
      this.quotesList.map((item, index) => {
        if(item == isBeingDelatedQuote) {
          this.quotesList.splice(index, 1);
        }
      })
    }
  }
}
</script>

<style>
.quotes-container {
  margin-top: 20px;
}
</style>