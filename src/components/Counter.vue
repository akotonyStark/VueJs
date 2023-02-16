<template>
  <div :style="{background: '#808080'}">
    <button @click="increment">Increment</button>
    <h3>{{ count }}</h3>
    <button @click="decrement">Decrement</button>
    <button @click="incrementBy(2, $event)">Increment by a number</button>
  </div>
    
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
    },
    incrementBy(num, event){
      this.count = this.count + num
      console.log(event)
    }
  }
}
</script>