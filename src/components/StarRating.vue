<template>
  <div class="starRating">
    <span v-for="index in starLimit" :key="index" class="starNoFill"></span>
    <div class="starRatingColored" :style="ratingWidthStyle">
      <span v-for="index in starLimit" :key="index" class="starFill"></span>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'StarRating',
    props: {
      rating: {
        type: Number,
        default: 0
      },
      starLimit: {
        type: Number,
        default: 5
      }
    },
    computed: {
      ratingWidth(){
        return this.rating / this.starLimit * 100 + '%'
      },
      ratingWidthStyle(){
        return `width: ${this.ratingWidth};`
      }
    }
  }
</script>

<style scoped>
.starRating{
  position: relative;
  display: inline-flex;
}
.starRatingColored{
  position: absolute;
  display: inline-flex;
  width: 0;
  height: 100%;
  top: 0;
  left: 0;
  overflow: hidden;
}
.starFill{
  display: inline-block;
  width: 34px;
  height: 34px;
  margin: 0 3px;
  flex-shrink: 0;
  background: url('../assets/starFill.svg') center no-repeat;
}
.starNoFill{
  display: inline-block;
  width: 34px;
  height: 34px;
  margin: 0 3px;
  flex-shrink: 0;
  background: url('../assets/starNoFill.svg') center no-repeat;
}

</style>