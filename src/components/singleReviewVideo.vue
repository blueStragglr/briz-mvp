<template>
  <div :id="'youtubeVideo' + yKey">
  </div>
</template>

<script>
  export default {
    name: "singleReviewVideo",
    props: ['iframeHTML', 'yKey'],
    mounted() {
      let videoDOM = document.getElementById("youtubeVideo" + this.yKey);
      videoDOM.innerHTML = this.iframeHTML;
    }
  }
</script>

<style scoped>
  div{
    text-align: center;
    margin-top: 20px;
  }
</style>