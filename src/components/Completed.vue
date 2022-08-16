<template>
    <div id="completed">
        
        <div class=" service-container">
            <h3 class="text-center">Completed</h3>
            <ul class="list-group list-group-flush text-center">
                <li v-for="data in prepared" :key="data.id" class="list-group-item">
                    <span>{{data.text}}</span>    
                </li>
                
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: "completed",
    props: ["prepared"]
}
</script>

<style scoped>
.list-group-item{
    background-color: #55828b;
    color: #fff;
}
ul{
    border-radius: 10px;

}

</style>