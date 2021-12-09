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
      let quoteCreatorField = document.querySelector('#quoteCreatorField').value;
      //console.log(quoteCreatorField);
      this.$emit("createdNewQuote", quoteCreatorField);
    }
  }
}
</script>

<style></style>