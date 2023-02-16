<template>
     <template v-for="(item, index) in names" :key="index">
     <h2 v-if="item === 'Bruce'">{{ item }}</h2></template>
</template>

<script>
export default {
    name:'ConditionalListRendering',
    data(){
        return{
            names: ['Tony', 'Bruce', 'Steven'],
                fullNames: [
                    {first:'Tony', last: "Stark"},
                    {first:'Bruce', last: 'Banner'},
                    {first:'Steven', last:'Stranage'}
                ],
        }
    }
}
</script>