<template>
    <div id="carservice">
        <div class=" service-container">
            <h3 class="text-center">Car Care Service</h3>
            <ul class="list-group list-group-flush">
                <li v-for="data in carCare" :key="data.id" class="mt-2">
                    <div v-if="!data.prepared" class="d-flex justify-content-between ">
                        <span v-if="data.careService == true" class="pt-2">{{data.text}}</span>
                        <div class="d-flex">
                            <input v-model="data.careService" type="checkbox" >
                            <input class="ms-2" v-model="data.prepared" type="checkbox">
                            
                        </div>
                    </div>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: "carservice",
    props: ["carCare"],

}
</script>

<style scoped>

ul{
    list-style-type: none;
    border-radius: 10px;
    color: #577590;
    font-weight: bold;

}
img{
    width:14px ;
}
button{
    background-color: #F4F6F5;
}
input{
    width: 20px;
}

</style>