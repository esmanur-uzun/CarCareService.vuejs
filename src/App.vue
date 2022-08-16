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
    carCareService(){
      return this.carList.filter((item) => item.careService)
    },
    completedCar(){
      return this.carList.filter((p) => p.prepared)
    }    
  },
  created (){
    this.carList = JSON.parse(localStorage.getItem('cars') || '[]')
  },
  watch:{
      carList:{
        deep: true,
        handler(){
          localStorage.setItem('cars',JSON.stringify(this.carList))
        }
      }
    }
}
</script>

<template>
  <div id="app">
    <div class=" app-container">
      <title-car @add-car="addCarBrand"></title-car>
      <div class=" d-flex justify-content-around mt-5 col-12 flex-wrap">
        <car-brands :myData="carList" @delete-item="deleteItem" class="col-lg-4 col-md-5 col-xs-12 col-10 mb-5"></car-brands>
        <care-service :carCare ="carCareService(event)" class="col-lg-4 col-md-5 col-xs-12 col-10"></care-service>
      </div>
      <div class="mt-5 d-flex justify-content-center">
        <completed @delete-item="deleteItem" :prepared ="completedCar(event)" class="col-lg-6 col-md-8 col-10"></completed>
      </div>
    </div>
  </div>
    
</template>

<style scoped>
.app-container{
  height: 100vh;
}
</style>
