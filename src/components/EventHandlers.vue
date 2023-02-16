<template>
    <h2>{{ name }} {{ age }}</h2>
    <button v-on:click="revealIdentity">Reveal Secret Identity</button>
    <button @click="name='Augustine'">Reveal Public Identity</button>
    <button @click="revealIdentity($event), increment()">Reveal Identity & Increase Age</button>
</template>


<script>
    export default {
        name: 'EventHandlers',
        data(){
            return{
                name: 'Augustine',
                age:29
            }
            
        },

        methods: {
            revealIdentity(e){
                 this.name = "I am Ironman"
                 console.log(e)
            },
            increment(){
                this.age++
            }
            
        }
    }
</script>