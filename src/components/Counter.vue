<template>
    <button @click="increment">Increment</button>
    <h3>{{ count }}</h3>
    <button @click="decrement">Decrement</button>
</template>

<script>
export default {
  name: 'CounterVue',
//   props: {
//     count: Number
//   },

  data(){
    return{
        count:10
    }
  },

  methods:{
    increment(){
        this.count++
    },
    decrement(){
        this.count--
    }
  }
}
</script>