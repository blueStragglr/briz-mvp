<template>
  <div id="mainBanner">
      <div class="slogan">
        Trendy K-beauty Rankings, Briz
      </div>
      <div class="searchBox">
        <input class="" type="text" placeholder="Search with category (i.e. Cream, Lotion, ...)">

      </div>
  </div>
</template>

<script>
  export default {
    name: "mainBanner"
  }
</script>

<style scoped>
#mainBanner{
  height: calc(80vh - 64px);
  /*padding-top: 64px;*/

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  align-content: center;
}

  .slogan {
    font-size: 24px;
    font-weight: 700;
    padding-bottom: 24px;
  }

  .searchBox{
    border: 1px solid #b45162;
    height: 32px;
    border-radius: 16px;
    width: 450px;

  }
</style>