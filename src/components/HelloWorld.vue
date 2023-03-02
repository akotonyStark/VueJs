<template>
  <div class="hello">
    <h1>{{ msg }}</h1><h2>{{ count }}</h2><button @click="incrementCount">Increment</button>


 
  </div>
</template>

<script>
import CounterMixin from '../mixins/utility'
export default {
  name: 'HelloWorld',
  mixins: [CounterMixin],
  props: {
    msg: String
  },
  data(){
    return {
      count: 100
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.hello{
  background-color: #42b983;
}
</style>


