<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <Counter/><br/><br/>
  <LoginForm/>
  <ConditionalRendering/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Counter from './components/Counter.vue';
import LoginForm from './components/LoginForm.vue';
import ConditionalRendering from './components/ConditionalRendering.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
    Counter, 
    LoginForm,
    ConditionalRendering
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
