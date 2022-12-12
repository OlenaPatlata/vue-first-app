<template>
  <div id="app">
    <h2>{{text}}</h2>
    <CustomInput
      :modelValue="text"
      @update:modelValue="text = $event"/>
    <ApartmentsList :items="apartmens">
      <template v-slot:apartment="{apartment}">
        <ApartmentsItem
          :key="apartment.id"
          :descr="apartment.descr" 
          :price="apartment.price" 
          :rating="apartment.rating"
          :imgSrc="apartment.imgUrl"
          @click="handleItemClick"
          />
      </template>
    </ApartmentsList>
      

  </div>
</template>

<script>
import ApartmentsList from './components/apartment/ApartmentsList.vue'
import apartmens from './components/apartment/apartment'
import ApartmentsItem from './components/apartment/ApartmentsItem.vue'
import CustomInput from './components/shared/CustomInput.vue'

export default {
  name: 'App',
  components: {
    ApartmentsList,
    ApartmentsItem,
    CustomInput
  },
  data(){
    return {
      apartmens,
      text: '',
    }
  },
  methods: {
    handleItemClick(){
      console.log('item click')
    }
  }
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
