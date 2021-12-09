<template>
  <div>
    <div class="progress-wrapper">
    <div class="progress" :style="[{'width': (quotesCount*10)+'%'}]">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    quotesCount: {
      type: Number,
      required: true,
    }
  }
}
</script>

<style scoped>
.progress-wrapper {
  width: 100%;
  border: 2px solid #222;
  border-radius: 5px;
  padding: 1px;
  margin-top: 30px;
  margin-bottom: 20px;
}

.progress {
  padding-top: 10px;
  padding-bottom: 10px;
  background-color: #2c2;
  margin: 0px;
}
</style>