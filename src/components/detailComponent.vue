<template>
  <div class="detail-component">
    <div class="basic-info">
      <div class="title">
        <span>
          {{this.cosmeticData.name}}
        </span>
        <div class="notes">
          <span v-for="(tag, index) in this.cosmeticData.notes" :key="index">{{tag}}</span>
        </div>
      </div>
      <div class="explanations">
        <div class="explanation-image">
          <!--          <img :src="this.cosmeticData.imageSource" alt="cosmetic image">-->
          <img src="../../src/assets/dermabiotics.jpg">
        </div>
        <div class="explanation-content">
          <div class="explanation-content-element">
            Brand: {{this.cosmeticData.brand}}
          </div>
          <div class="explanation-content-element">
            Price: {{returnWithCommas(this.cosmeticData.price)}} KRW &nbsp;
            <span>(~= {{returnWithCommas(Math.round(this.cosmeticData.price/110)/10)}} USD)</span>
          </div>
          <div class="explanation-content-element">
            Volume: {{this.cosmeticData.volume}}
          </div>
          <div class="explanation-link">
            <a :href="this.cosmeticData.resellerLink" target="_blank">Find Online Reseller</a>
          </div>
        </div>
      </div>
      <div class="reviews">
        <div class="rating">
          Rating
          <div class="rating-star">
            <div class="rating-cover" :style="{width: this.cosmeticData.rating[0] / 5.0 * 100 + '%'}"></div>
          </div>
          <br/>
          <span class="rating-info">
            ({{this.cosmeticData.rating[0]}} / 5.0, {{this.cosmeticData.rating[1]}} participants)
          </span>
          <div class="rating-element">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis tristique ipsum a urna ultrices fermentum. Ut
            rutrum ex ut auctor vehicula. Fusce quis eleifend elit. Mauris quis nisl at erat tempus consectetur. Cras
            quis suscipit enim, vitae auctor mauris. Morbi diam odio, pretium pharetra neque et, aliquet pellentesque
            dui. Etiam consectetur dapibus tellus vel finibus. Morbi nec malesuada magna, gravida vehicula turpis. Duis
            dolor quam, rhoncus ac urna id, suscipit mattis sapien. Praesent pretium, massa vitae pellentesque vehicula,
            mi diam tristique leo, quis congue nibh diam faucibus lorem.
          </div>
        </div>

        <div class="review-video-title">
          Reviews
          <div class="review-videos">
            <!--  TODO: Change embeddedLink1,2,3 to embeddedLink = [link1, link2, link3...] -->
            <single-review-video :iframe-h-t-m-l="this.cosmeticData.embeddedLink1" :y-key="0"></single-review-video><br/>
            <single-review-video :iframe-h-t-m-l="this.cosmeticData.embeddedLink2" :y-key="1"></single-review-video><br/>
            <single-review-video :iframe-h-t-m-l="this.cosmeticData.embeddedLink3" :y-key="2"></single-review-video>
          </div>
        </div>
      </div>
    </div>
    <comments></comments>
  </div>
</template>

<script>
  import SingleReviewVideo from "./singleReviewVideo";
  import Comments from "./comments";

  export default {
    components: {Comments, SingleReviewVideo},
    props: ['componentHash', 'query'],
    name: "detailComponent",
    data() {
      const hash = this.componentHash;
      let cosmeticData = {'name': '', 'brand': '', 'rank': '', 'resellerLink': '', 'imageSource': '', 'volume': '',
        'price': '', 'notes': '', 'rating': '', 'embeddedLink1': '', 'embeddedLink2': '', 'embeddedLink3': ''};
      return {
        hash,
        cosmeticData
      }
    },


    created() {
      // TODO(with back-end): Call Axios with this.$router.query when component mounted
      // this.cosmeticData = []
      const category = Number(this.$route.query.c);
      const itemIndex = Number(this.$route.query.i);

      // 'skinCare', 'cleansing', 'maskNpack', 'base', 'eyes', 'lips', 'body', 'suncare'
      switch (category) {
        case 0:
          this.cosmeticData = this.$store.state.rawData.skinCare[itemIndex];
          break;
        case 1:
          this.cosmeticData = this.$store.state.rawData.cleansing[itemIndex];
          break;
        case 2:
          this.cosmeticData = this.$store.state.rawData.maskNpack[itemIndex];
          break;
        case 3:
          this.cosmeticData = this.$store.state.rawData.base[itemIndex];
          break;
        case 4:
          this.cosmeticData = this.$store.state.rawData.eyes[itemIndex];
          break;
        case 5:
          this.cosmeticData = this.$store.state.rawData.lips[itemIndex];
          break;
        case 6:
          this.cosmeticData = this.$store.state.rawData.body[itemIndex];
          break;
        case 7:
          this.cosmeticData = this.$store.state.rawData.suncare[itemIndex];
          break;
      }

    },
    methods: {
      returnWithCommas(numberToChange) {
        return numberToChange.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
      },
    }
  }
</script>

<style scoped>
  .detail-component {
    padding: 40px;
    max-width: 768px;

    margin: 20px auto;
  }

  .title {
    font-size: 24px;
    font-weight: 700;
  }


  .notes {
    font-size: 12px;
    padding: 6px 0 12px;
  }

  .notes > span {
    padding: 2px 12px;
    background-color: #b45162;
    color: #ffffff;
    border-radius: 8px;
    margin-right: 4px;

  }

  .explanations {
    display: flex;
  }

  .explanation-image > img {
    width: 100%;
  }

  .explanation-image {
    flex: 1;
  }

  .explanation-content {
    flex: 1;
    padding-left: 20px;

  }

  .explanation-content-element {
    padding: 15px 5px;
    border-bottom: 1px solid #e9e9e9;
  }

  .explanation-content-element > span {
    /*float: right;*/
    font-size: 13px;
    color: #4d4d4d;
  }

  .explanation-content-element > a:hover {
    opacity: 1;
  }

  .explanation-link {
    text-align: center;
    padding: 15px;
  }

  .explanation-link > a {
    text-decoration: none;
    transition: .25s ease-in-out;
    opacity: .9;
    width: 70%;
    background-color: #2c3e50;
    color: #ffffff;
    padding: 4px 12px;
    border-radius: 4px;
    cursor: pointer;
  }


  .rating-star {
    width: 108px;
    display: inline-block;
    position: relative;
    height: 18px;
    vertical-align: middle;

  }

  .rating-cover {
    background-image: url("../assets/2x/rating-star.png");
    background-size: cover;
    overflow: hidden;
    height: 18px;
    vertical-align: sub;
  }

  .rating-star img {
    position: absolute;
    height: 18px;
  }

  .rating-star:before {
    position: absolute;
    left: 0;
    top: 0;
    height: 36px;
    width: 100%;


  }

  .rating {
    margin-top: 16px;
    font-size: 21px;
    font-weight: 700;
  }

  .rating-info {
    font-size: 12px;
    color: #4d4d4d;
  }

  .rating-element {
    font-size: 14px;
    font-weight: 400;
  }

  .review-video-title {
    margin-top: 16px;
    font-size: 21px;
    font-weight: 700;
  }

  .review-videos {
    /*display: flex;*/
  }


</style>