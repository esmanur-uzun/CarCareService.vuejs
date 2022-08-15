<template>
    <div id="carbrand">
        <div class=" car-container">
            <ul class="list-group list-group-flush">
                <li v-for="item in myData" :key="item.id" class="list-group-item d-flex justify-content-between">
                    <span class="pt-2">{{item.text}}</span>
                    <div>
                        <button @click="$emit('care-item',item)"  class="btn me-1"><img src="../assets/gear-solid.svg" alt=""></button>
                        <button @click="$emit('delete-item',item)" class="btn"><img src="../assets/trash-can-solid.svg" alt=""></button>                       
                    </div>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    props: ["myData"],
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