<template lang="en">
    <div>
        <h1 :style="{color:'red'}">{{error}}</h1>
        <h2>Volume tracker (0-20)</h2>
        <h3>Current Volume: {{volume}} </h3> 
        <button @click="volume++">Increase </button>
        <button @click="volume--">Decrease</button><br/>
        <input type="text" v-model="movie"/>
        <input type="text" v-model="movieInfo.title" placeholder="movie title"/>
        <input type="text" v-model="movieInfo.actor" placeholder="actor"/>
        <button @click="movieList.push('Movie 3')">Add Movie</button>
    </div>
</template>
<script>
export default {
    name: 'WatchersApp',
    data(){
        return {
            volume: 5,
            error:'',
            movie:'Infinity War',
            movieInfo: {
                title:'',
                actor:''
            },
            movieList: ['Movie 1', 'Movie 2']
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
            else{
                this.error = ""
            }
        },
        movie:{
            handler(newValue){
            console.log(`calling api search for ${newValue}`)
        },
        immediate:true
        },
        movieInfo:{
            handler(newValue){
            console.log(`calling api search for movieTitle ${newValue.title} and actor ${newValue.actor}`)
        },
        //use deep property you want to watch inner states of an object
        deep:true
        },
        movieList:{
            handler(newValue){
                console.log(`Updated List: ${newValue}`)
            },
            deep: true
        }
    }
}
</script>
<style>
    
</style>