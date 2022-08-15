<script >
import CarBrands from './components/CarBrands.vue'
import CareService from './components/CareService.vue'
import Completed from './components/Completed.vue'
import TitleCar from './components/TitleCar.vue'
// import { ref, computed, reactive } from "vue";

export default{
  components: { TitleCar, CarBrands, CareService, Completed },
  name: "app",
  data(){
    return{
      carList : [],
    }
  },
  methods:{
    addCarBrand(carBrand){
      if(carBrand === ""){
        return
      }
      this.carList.push({
        text: carBrand,
        id: new Date().getTime(),
        careService: false,
        prepared: false

      })
     
    },
    deleteItem(item){
      this.carList = this.carList.filter( t => t !== item)
    },
    carCareService(event){
      console.log(event)
      return this.carList.filter((item) => item.careService)
      // return event.careService

    }
  }
}
</script>

<template>
  <div id="app">
    <div class=" app-container">
      <title-car @add-car="addCarBrand"></title-car>
      <div class="row d-flex justify-content-around mt-5">
        <car-brands :myData="carList" @delete-item="deleteItem" @care-item="carCareService" class="col-lg-4 col-md-5 col-9 mb-4"></car-brands>
        <care-service :carCare ="carCareService(event)" class="col-lg-4 col-md-5 col-9"></care-service>
      </div>
      <div class="mt-5 d-flex justify-content-center">
        <completed class="col-lg-6 col-md-8 col-10"></completed>
      </div>
    </div>
  </div>
    
</template>

<style scoped>
.app-container{
  height: 100vh;
}
</style>
