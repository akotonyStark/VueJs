<template>
    <h4>This is Tab A</h4>
    <input type="text" placeholder="FullName" v-model="name"/>
</template>


<script>
export default {
    name:'TabA',
    data(){
        return{
            name:''
        }
       
    }
}
</script>

<style scoped>
    h4{
        color: rgb(175, 149, 3)
    }
</style>