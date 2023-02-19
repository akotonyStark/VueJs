<template lang="en">
    <div>
        <h1 :style="{color:'red'}">{{error}}</h1>
        <h2>Volume tracker (0-20)</h2>
        <h3>Current Volume: {{volume}} </h3> 
        <button @click="volume++">Increase </button>
        <button @click="volume--">Decrease</button>
    </div>
</template>
<script>
export default {
    name: 'WatchersApp',
    data(){
        return {
            volume: 5,
            error:''
        }
    },
    computed:{
        
    },
    methods:{

    },
    watch:{
        volume(newValue, oldValue){
            if(newValue > oldValue && newValue == 16){
                this.error = "Danger! Listening at high volumes may damage your hearing"
            }
            // else{
            //     this.error = ""
            // }
        }
    }
}
</script>
<style lang="">
    
</style>