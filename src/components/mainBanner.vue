<template>
  <div id="mainBanner">
      <div class="slogan">
        Trendy K-beauty Rankings, Briz.
      </div>
      <div class="searchBox">
        <input class="search-input" type="text" placeholder="Search with category (i.e. Cream, Lotion, ...)">
        <button class="search-button" type="button" @click="search()"> GO </button>
      </div>
  </div>
</template>

<script>
  export default {
    name: "mainBanner",
    data() {
      return {

      }
    }
  }
</script>

<style scoped>
#mainBanner{
  height: calc(100vh - 64px);
  /*padding-top: 64px;*/
  background-image: url("../assets/main.jpg");
  -webkit-background-size: cover;
  background-size: cover;
  background-position: center center;
  
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  align-content: center;
  padding-bottom: 10vh
}

  .slogan {
    color: #ffffff;
    font-size: 24px;
    font-weight: 700;
    padding-bottom: 24px;
  }

  .searchBox:focus-within {
    border: 1px solid #b45162;
  }

  .searchBox{
    background-color: #fff;
    transition: border .25s ease-in;
    height: 48px;
    border-radius: 24px;
    width: 450px;
    text-align: center;
    outline: none;
    box-shadow: 0 0 2px 2px rgba(0,0,0,0.05);
  }
  .search-input{
    margin: 6px 0 ;
    border-radius: 16px;
    height: 32px;
    padding: 10px;
    border: none;
    width: 370px;
    outline: none;
  }
  .search-button{
    width: 46px;
    height: 46px;
    float: right;
    border-radius: 23px;
    border: transparent;
    cursor: pointer;
    transition: .25s ease-in-out;
  }
  .searchBox:focus-within .search-button,
  .search-button:hover{
    background-color: rgba(228, 101, 131, 0.15);
    color: #b45162;
  }

</style>