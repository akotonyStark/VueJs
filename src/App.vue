<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <h2>Logged in as {{ username }}</h2>
  <pre>These are components with props</pre>
  <hr/>
  <HeroNames name="Tony Stark" heroName="Ironman"/>
  <HeroNames name="Bruce Banner" heroName="Hulk"/>
  <HeroNames name="Peter Parker" hero-name="Spiderman"/>
  <HeroNames :name="name" :heroName="alias"/>
  <ArticleComponent id="my-article" title="The Purge on Elm street" :numberOfLikes="50" :isPublished="true"/>
  <hr/>
  <ChildComponent/>
  <hr/>
  <pre>How Watchers Work - similar to useEffect in react</pre>
  <hr/>
  <Watchers/>
  <hr/>
  <ComputedProperties/>
  <FormHandling/>
  <Counter/><br/><br/>
  <LoginForm/>
  <ConditionalRendering/>
  <ListRendering/>
  <DynamicForm/>
  <ConditionalListRendering/>
  <UsingFunctions/>
  <EventHandlers/>
 
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Counter from './components/Counter.vue';
import LoginForm from './components/LoginForm.vue';
import ConditionalRendering from './components/ConditionalRendering.vue';
import ListRendering from './components/ListRendering.vue';
import DynamicForm from './components/DynamicForm.vue';
import ConditionalListRendering from './components/ConditionalListRendering.vue';
import UsingFunctions from './components/UsingFunctions.vue';
import EventHandlers from './components/EventHandlers.vue';
import FormHandling from './components/FormHandling.vue';
import ComputedProperties from './components/ComputedProperties.vue';
import Watchers from './components/Watchers.vue';
import HeroNames from './components/HeroNames.vue'
import ArticleComponent from './components/Article.vue'
import ChildComponent from './components/ChildComponent.vue';

export default {
  name: 'App',
  data(){
    return{
    name: 'Augustine',
    alias: 'Mr. Stark',
    username: 'akotonyStark'
    }
  },
  provide(){
    return{
      username: this.username
    }
  },
  components: {
    HelloWorld,
    Counter,
    LoginForm,
    ConditionalRendering,
    ListRendering,
    DynamicForm,
    ConditionalListRendering,
    UsingFunctions,
    EventHandlers,
    FormHandling,
    ComputedProperties,
    Watchers,
    HeroNames,
    ArticleComponent,
    ChildComponent
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  /* margin-top: 60px; */
}
</style>


