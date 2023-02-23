

<template lang="">
    <div>
        <h2>{{title}}</h2>
        <GrandChildComponent/>
    </div>
</template>
<script>
import GrandChildComponent from './GrandChildComponent.vue'
export default {
    name:'ChildComponent',
    data(){
        return{
            title: 'This is a Child Component of App component'
        }
    },
    components: {
        GrandChildComponent
    }
}
</script>
<style lang="">
    
</style>