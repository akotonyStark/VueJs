<template>
    <h3 v-for="(item, index) in names" :key="index">{{ index+1 }} {{ item }}</h3>
    <h3 v-for="(name, index) in fullNames" :key="index">{{ index+1 }} {{ name.first }} {{ name.last }}</h3>
    <h3 v-for="(array, index) in arrayOfArrays" :key="index">{{array}}</h3>

    <div v-for="actor in actors" :key="actor.name">
        <h3 :style="{color:'orange'}">{{ actor.name }}</h3>
        <h2 v-for="movie in actor.movies" :key="movie">{{movie}}</h2>
    </div>
    <h2 v-for="(value, key, index) in myInfo" :key="value">{{index}} {{ key }} {{ value }}</h2>

    <template v-for="name in names" :key="name">
        <h3 :style="{color:'orange'}">{{ name }}</h3>
        <hr/>
        
    </template>
</template>


<script>
    export default {
        name: "ListRendering",
        data(){
            return{
                names: ['Tony', 'Bruce', 'Steven'],
                fullNames: [
                    {first:'Tony', last: "Stark"},
                    {first:'Bruce', last: 'Banner'},
                    {first:'Steven', last:'Stranage'}
                ],
                arrayOfArrays: [
                    ['Bucky', 'Bambmi', 'Simba'],
                    ['Loki', 'Vero', 'Charles']
                ],
                actors:[
                    {
                        name: 'Christian Bale',
                        movies: ['Batman', 'The Prestige, American Psycho']
                    },
                    {
                        name: 'Leonardo DiCaprio',
                        movies: ['Titanic', 'What is eating Gilber Grape', 'Catch me if you can', 'Inception']
                    }
                ],
                myInfo: {
                    name: 'Augustine',
                    age: 29,
                    gender: 'Male'
                }

            }
        }
    }
</script>