<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <Counter/><br/><br/>
  <LoginForm/>
  <ConditionalRendering/>
  <ListRendering/>
  <DynamicForm/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Counter from './components/Counter.vue';
import LoginForm from './components/LoginForm.vue';
import ConditionalRendering from './components/ConditionalRendering.vue';
import ListRendering from './components/ListRendering.vue';
import DynamicForm from './components/DynamicForm.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
    Counter,
    LoginForm,
    ConditionalRendering,
    ListRendering,
    DynamicForm
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
