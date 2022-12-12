<template>
  <div v-if="isVisible">
    <h1 >Directives</h1>
    <ul>
      <template v-for="fruit in fruits" >
        <li class="fruit" v-if="fruit === 'banana'" :key="fruit">{{fruit}}</li>
      </template>
    </ul>
    <ul>
      <li v-for="(car, key) in cars" :key="key">{{`color ${key}: ${car.color}`}}</li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: 'DirectivesTest',
    data(){
      return {
        isVisible: true,
        fruits: ['kiwi', 'apple', 'lime', 'banana'],
        cars: {
          audi: {
            color: "black"
          },
          bmv: {
            color: "red"
          }
        }
      }
    }
  }
</script>

<style lang="scss" scoped>
  .fruit{
    color: chocolate;
    font-weight: 700;
  }
</style>