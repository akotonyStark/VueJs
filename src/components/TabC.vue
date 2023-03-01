<template>
    <h4>This is Tab C</h4>
    <textarea type="text" placeholder="Cover Letter" v-model="letter"></textarea>
</template>


<script>
export default {
    name:'TabC',
    data(){
        return{
            letter: ''
        }
    }
}
</script>

<style>

</style>