<template>
  <div>
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

</style>