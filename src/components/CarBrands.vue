<template>
    <div id="carbrand">
        <div class=" car-container">
            <h3 class="text-center">Car Brand List</h3>
            <ul  class="list-group list-group-flush">
                <li class="pt-2" v-for="item in myData" :key="item.id">
                    <div v-if="!item.careService" class="d-flex justify-content-between " >
                        <span   class="pt-2">{{item.text}}</span>
                        <div  class="d-flex">
                            <input id="completed" type="checkbox" v-model="item.careService">
                            <button @click="$emit('delete-item',item)" class="btn ms-2"><img src="../assets/trash-can-solid.svg" alt=""></button> 
                        </div>
                                              
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
ul{
    border-radius: 10px;
    list-style-type: none;
    color: #577590;
    font-weight: bold;

}
img{
    width:14px ;
}
button{
    background-color: #577590;
}
input{
    width: 15px;
}
</style>