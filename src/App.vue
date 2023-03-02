<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->

  <HelloWorld msg="Welcome to Your Vue.js App" />

  <LoadPosts/>

  <button @click="showModal = true">Show Modal</button>
  <teleport to="#portal-root">
    <Portal />

    <ModalUI v-show="showModal" @close="showModal = false">
      This is a modal message
    </ModalUI>
  </teleport>





  <div>
    <pre>Handling Tabbed - Dynamic Components</pre>
    <button @click="activeTab = 'TabA'">Tab A</button>
    <button @click="activeTab = 'TabB'">Tab B</button>
    <button @click="activeTab = 'TabC'">Tab C</button><br />

    <code>We can use this approach</code>
    <keep-alive>
      <component v-bind:is="activeTab" />
    </keep-alive>

    <br />

    <code>Or we can use this approach</code>
    <TabA v-if="activeTab === 'TabA'" />
    <TabB v-if="activeTab === 'TabB'" />
    <TabC v-if="activeTab === 'TabC'" />
  </div>



  <button @click="showPopup = true">Open Popup</button>
  <Popup v-show="showPopup" @close="closePopup" />
  <InputComponent v-model="description" />
  <pre>{{ description }}</pre>
  <Card>
    <h3>Some content</h3>
  </Card>
  <Card>
    <img src="https://picsum.photos/200">
  </Card>
  <Card>
    <template v-slot:header>
      <h2>Header</h2>
    </template>
    <template v-slot:default><img src="https://picsum.photos/200"></template>
    <template v-slot:footer><button>View Details</button></template>
  </Card>
  <hr />
  <pre>Slot Props</pre>
  <NameList>
    <template v-slot:default="slotProps">
      {{ slotProps.firstName }} {{ slotProps.lastName }}
    </template>
  </NameList>

  <NameList>
    <template v-slot:default="slotProps">
      {{ slotProps.lastName }}, {{ slotProps.firstName }}
    </template>
  </NameList>


  <h2>Logged in as {{ username }}</h2>
  <pre>These are components with props</pre>
  <hr />
  <HeroNames name="Tony Stark" heroName="Ironman" />
  <HeroNames name="Bruce Banner" heroName="Hulk" />
  <HeroNames name="Peter Parker" hero-name="Spiderman" />
  <HeroNames :name="name" :heroName="alias" />
  <ArticleComponent id="my-article" title="The Purge on Elm street" :numberOfLikes="50" :isPublished="true" />
  <hr />
  <ChildComponent />
  <hr />
  <pre>How Watchers Work - similar to useEffect in react</pre>
  <hr />
  <Watchers />
  <hr />
  <ComputedProperties />
  <FormHandling />
  <Counter /><br /><br />
  <LoginForm />
  <ConditionalRendering />
  <ListRendering />
  <DynamicForm />
  <ConditionalListRendering />
  <UsingFunctions />
  <EventHandlers />
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
import Popup from './components/Popup.vue';
import InputComponent from './components/Input.vue';
import Card from './components/Card.vue';
import NameList from './components/NameList.vue';
import TabA from './components/TabA.vue'
import TabB from './components/TabB.vue'
import TabC from './components/TabC.vue'
import Portal from './components/Portal.vue';
import ModalUI from './components/Modal.vue';
import LoadPosts from './components/APIComponent.vue'

export default {
  name: 'App',
  data() {
    return {
      name: 'Augustine',
      alias: 'Mr. Stark',
      username: 'akotonyStark',
      showPopup: false,
      description: '',
      activeTab: 'TabA',
      showModal: false
    }
  },
  methods: {
    closePopup(data) {
      this.showPopup = false
      alert(data)
    }
  },
  provide() {
    return {
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
    ChildComponent,
    Popup,
    InputComponent,
    Card,
    NameList, TabA, TabB, TabC,
    Portal,
    ModalUI,
    LoadPosts

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


