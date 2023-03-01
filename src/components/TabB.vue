<template>
    <h4>This is Tab B</h4>
    <input type="text" placeholder="Job Title" v-model="jobTitle"/>
</template>


<script>
export default {
    name:'TabB',
    data(){
        return{
            jobTitle: ''
        }
    }
}
</script>

<style scoped>
    h4{
        color: #819700
    }
</style>