<template>
  <div class="about">
    <detail-component :componentHash = "'itemURLhash'"/>
  </div>
</template>
<script>
  import DetailComponent from "../components/detailComponent";
  export default {
    components: {DetailComponent}
  }
</script>