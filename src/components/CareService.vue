<template>
    <div id="carservice">
        {{carCare}}
        <div class=" service-container">
            <ul class="list-group list-group-flush">
                
                <li v-for="data in carCare" :key="data.id" class="list-group-item d-flex justify-content-between">
                    <span v-if="data.careService == true" class="pt-2">{{data.text}}</span>
                    <div>
                        <button class="btn me-1"><img src="../assets/arrow-rotate-left-solid.svg" alt=""></button>
                        <button class="btn"><img src="../assets/check-solid.svg" alt=""></button>                       
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
.list-group-item{
    background-color: #577590;
    color: #fff;
}
ul{
    border-radius: 10px;

}
img{
    width:14px ;
}
button{
    background-color: #F4F6F5;
}
</style>