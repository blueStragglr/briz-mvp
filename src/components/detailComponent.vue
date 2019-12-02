<template>
  <div class="detail-component">
    <div class="basic-info">
      {{this.$route.query}}
      <div class="title">
        <span>
          Derma Biotics
        </span>
      </div>
      <div class="explanations">
        <div class="explanation-image">
          <img src="../../src/assets/dermabiotics.jpg">
        </div>
        <div class="explanation-content">
          <div class="explanation-content-element">
            price: 10.99$
          </div>
          <div class="explanation-content-element">
            price: 10.99$
          </div>
          <div class="explanation-content-element">
            price: 10.99$
          </div>
          <div class="explanation-content-element">
            price: 10.99$
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['componentHash', 'query'],
    name: "detailComponent",
    data() {
      const hash = this.componentHash;
      return {
        hash
      }
    },


    mounted(){
      // Call Axios with componentHash when component mounted

    }
  }
</script>

<style scoped>
  .detail-component{
    padding: 40px;
    max-width: 768px;

    margin: 20px auto;
  }
  .title{
    font-size: 18px;
    font-weight: 800;
  }

  .title > span{

  }

  .explanations{
    display: flex;
  }
  .explanation-image>img{
    width: 100%;
  }
  .explanation-image{
    flex: 1;
  }
  .explanation-content{
    flex: 1;
    padding-left: 20px;

    display: flex;
    flex-direction: column;
  }
  .explanation-content-element{
    padding: 15px 5px;
    flex: 1;
    border-bottom: 1px solid #e9e9e9;
  }


</style>