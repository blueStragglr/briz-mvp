<template>
  <div class="detail-component">
    <div class="">

    </div>
    {{this.hash}}
  </div>
</template>

<script>
  export default {
    props: ['componentHash'],
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

</style>