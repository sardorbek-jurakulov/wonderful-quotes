<template>
  <form 
    action="https://echo.htmlacademy.ru" 
    method="POST" id="quoteCreatorForm" 
    @submit="newQuoteRegistrator"
    :class="{'quotes-are-owerflowed': isQuotesCountOwerflow}" 
    >
      <label for="quoteCreatorField">Quote</label>
      <textarea 
        name="quoteCreatorField" 
        id="quoteCreatorField" 
        autofocus
        :disabled="isQuotesCountOwerflow"
      ></textarea>
      <button type="submit">Add Quote</button>
  </form>
</template>

<script>
export default {
  props: {
    isQuotesCountOwerflow:{
      type: Boolean,
      required: false,
      default: false,
    }
  },
  methods: {
    newQuoteRegistrator(evt) {
      evt.preventDefault();
      if((document.querySelector('#quoteCreatorField').value.trim() != '') && (this.isQuotesCountOwerflow != true)) {
        this.$emit("createdNewQuote", document.querySelector('#quoteCreatorField').value.trim());
        document.querySelector('#quoteCreatorField').value = null;
      }
    }
  }
}
</script>

<style scoped>
  .quotes-are-owerflowed {
    opacity: 0.5;
  }
</style>