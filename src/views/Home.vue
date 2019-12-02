<template>
  <div class="home">
    <main-banner/>
    <ranking/>
  </div>
</template>

<script>
// @ is an alias to /src

import MainBanner from "../components/mainBanner";
import Ranking from "../components/ranking";
export default {
  name: 'home',
  components: {
    Ranking,
    MainBanner
  }
}
</script>
