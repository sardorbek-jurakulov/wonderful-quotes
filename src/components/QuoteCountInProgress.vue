<template>
  <div>
    <div class="progress-wrapper">
      <div class="progress" :style="[{'width': (quotesCount*10)+'%'}]">
        {{ quotesCount }} / 10
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
  },watch: {
    quotesCount() {
      if(this.quotesCount < 0) {
        this.quotesCount = 0;
      } else if(this.quotesCount > 10) {
        this.quotesCount = 10;
      }
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
  display: flex;
  align-items: center;
  justify-content: center;
  padding-top: 10px;
  padding-bottom: 10px;
  background-color: #2c2;
  margin: 0px;
  color: #fff;
  transition: width ease 0.5s;
}
</style>