<template>
  <form action="https://echo.htmlacademy.ru" method="POST" id="quoteCreatorForm" @submit="newQuoteRegistrator">
    <label for="quoteCreatorField">Quote</label>
    <input type="text" name="quoteCreatorField" id="quoteCreatorField" autofocus>
    <button type="submit">Add Quote</button>
  </form>
</template>

<script>
export default {
  methods: {
    newQuoteRegistrator(evt) {
      evt.preventDefault();
      this.$emit("createdNewQuote", document.querySelector('#quoteCreatorField').value);
      document.querySelector('#quoteCreatorField').value = null;
    }
  }
}
</script>

<style></style>