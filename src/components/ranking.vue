<template>
  <div class="ranking-container">
    <div class="component-label">
      <span>
        K-Cosmetic Ranking with Categories
      </span>
    </div>
    <div class="ranking-category">
      <button v-for="(category, index) in rankingCategory" :key="index"
              @click="shiftCategory(index)" :class="{'selected': index === rankingIndex}">
        {{category}}
      </button>
    </div>
    <div class="ranking-element">
      <div class="ranking-list-element" v-for="(singleData, index) in rankingData" :key="index"
            @click="getElmPage(rankingIndex, index)">
        <div class="ranking-label">
          <div class="ranking-rank">{{singleData.rank}}</div>
        </div>

        <div class="ranking-data">
          <div class="ranking-name">{{singleData.name}}</div>
          <div>Brand: {{singleData.brand}}</div>
          <span class="divider">|</span>
          <div>{{singleData.volume}}</div>
          <span class="divider">|</span>
          <div>{{singleData.imgSource}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "ranking",
    data() {
      let rankingIndex = 0;
      let rankingData = this.$store.state.rawData.skinCare;
      let rankingCategory = ['Skin care', 'Cleansing', 'Mask & Pack', 'Base', 'Eyes', 'Lips', 'Body', 'Sun Care'];

      return {
        rankingIndex,
        rankingData,
        rankingCategory
      }
    },
    methods: {
      shiftCategory(index) {


        this.rankingIndex = index;
      },
      getElmPage(category, idx) {
        console.log(category, idx);
        let routeData =  this.$router.resolve({path: 'detailPage', query: {c: category, i: idx}});
        window.open(routeData.href, '_blank');
      }
    }
  }
</script>

<style scoped>
  .ranking-container {
    max-width: 768px;
    margin: 150px auto 30px;
  }

  .component-label{
    display: inline-block;
    font-size: 24px;
    font-weight: 600;
    position: relative;
  }

  .component-label>span:after{
    content: ' ';
    position: absolute;
    height: 12px;
    width: calc(100% + 10px);
    left: -5px;
    bottom: 5px;
    background-color: rgba(228, 101, 131, 0.15);
  }
  .ranking-category{
    display: flex;
    flex-wrap: wrap;
    margin: 36px 20px 20px;
  }

  .ranking-category>button{
    flex: 1 1 25%;
    min-width: 120px;
    border: none;
    border-right: 1px solid #e9e9e9;
    cursor: pointer;
    background-color: transparent;
    font-size: 16px;
    padding: 12px;
    font-weight: 600;
    outline: none;
    transition: 0.5s ease-in-out;
  }


  .ranking-category>button:nth-child(1),
  .ranking-category>button:nth-child(2),
  .ranking-category>button:nth-child(3),
  .ranking-category>button:nth-child(4){
    border-bottom: 1px solid #e9e9e9;
  }

  .ranking-category>button:nth-child(4),
  .ranking-category>button:last-child{
    border-right: none;
  }

  .ranking-category>button.selected{
    background-color: rgba(228, 101, 131, 0.07);
    color: #b45162;
  }

  .ranking-list-element{
    padding: 10px;
    border-bottom: 1px solid #e9e9e9;
    display: flex;
    cursor: pointer;
    transition: 0.25s ease-in-out;
  }

  .ranking-list-element:hover{
    background-color: rgba(30,20,10, 0.02);
  }

  .ranking-label {
    flex: none;
    width: 48px;
  }

  .ranking-list-element:nth-child(1) .ranking-rank{
    color: #b45162;
    font-weight: 600;
    font-size: 21px;
  }
  .ranking-list-element:nth-child(2) .ranking-rank{
    color: #dec4a8;
    font-weight: 600;
    font-size: 21px;
  }
  .ranking-list-element:nth-child(3) .ranking-rank{
    color: #393638;
    font-weight: 600;
    font-size: 21px;
  }
  .ranking-rank{
    font-size: 18px;
  }


  .ranking-data{
    display: flex;
    flex-wrap: wrap;
  }
  .ranking-name{
    flex: 1 1 100%;
    margin: 3px 0 12px;
    font-size: 16px;
    font-weight: 500;
  }
  .divider{
    padding: 0 10px;
  }
</style>