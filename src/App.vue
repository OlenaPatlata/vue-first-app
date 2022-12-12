<template>
  <div id="app">
    <ApartmentsList :items="apartmens">
      <template v-slot:apartment="{apartment}">
        <ApartmentsItem
          :key="apartment.id"
          :descr="apartment.descr" 
          :price="apartment.price" 
          :rating="apartment.rating"
          :imgSrc="apartment.imgUrl"/>
      </template>
    </ApartmentsList>
      

  </div>
</template>

<script>
import ApartmentsList from './components/apartment/ApartmentsList.vue'
import apartmens from './components/apartment/apartment'
import ApartmentsItem from './components/apartment/ApartmentsItem.vue'

export default {
  name: 'App',
  components: {
    ApartmentsList,
    ApartmentsItem
  },
  data(){
    return {
      apartmens
    }
  },
}
</script>

<style>
#app {
  font-family: Montserrat, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
