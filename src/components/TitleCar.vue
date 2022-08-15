<template>
    <div id="cartitle">
        <div>
            <div class="title pb-2 mb-5 ">
                <h2 class="text-center">Car Care Service</h2>
            </div>
            <div class="col-lg-6 container">
                <form @submit.prevent="sendCarBrand" class=" col-lg-8 pt-5 m-auto ">
                    <div class="input-group">
                        <input v-model="newCar" type="text" class="form-control" placeholder="Add Car Brand" aria-label="Add Car Brand" aria-describedby="button-addon2">
                        <!-- <button  class="btn btn-submit btn-outline-secondary" type="button" id="button-addon2">Button</button> -->
                    </div>
                    <hr>
                 </form>
            </div>
           
        </div>
    </div>
       
</template>

<script>
export default {
    data(){
        return {
            newCar :"",
        }
    },
    methods:{
        sendCarBrand(){
            this.$emit("add-car",this.newCar)
            this.newCar = ""
           
        }
    }
}
</script>

<style scoped>
.title{
  background-color: #2d3142;
  color: #bfc0c0;
}

.btn-submit{
    background-color: #003459;
    color: #bfc0c0;
}
</style>