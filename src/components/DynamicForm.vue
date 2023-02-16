<template>
    <template v-for="name in names" :key="name">
        <label >{{ name }} : </label>
        <input placeholder="Last Name" />
    </template>
<br/>

    <button @click="shuffle">Shuffle</button>

</template>


<script>
export default {
    name:'DynamicForm',
    data(){
        return{
         names: ['Tony', 'Bruce', 'Steven'],
        }
    },
    methods:{
        shuffle(){
            console.log(this.names)
            this.names = this.names.sort(() => 0.5 - Math.random());
        }
    }
}
</script>