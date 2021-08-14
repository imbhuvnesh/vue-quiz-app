<template>
  <div class="result">
    <div class="title">{{ results[resultIdx].title }}</div>
    <div class="desc">{{ results[resultIdx].desc }}</div>
  </div>
</template>

<script>
export default {
  props: ["totalCorrect", "results"],
  computed: {
    resultIdx() {
      let index = 0;
      this.results.forEach((r, i) => {
        if (this.totalCorrect >= r.min && this.totalCorrect <= r.max) {
          console.log(this.totalCorrect);
          index = i;
        }
      });
      return index;
    },
  },
};
</script>

<style lang="scss" scoped>
</style>