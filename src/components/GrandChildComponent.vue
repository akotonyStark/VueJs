<template lang="">
    <div>
        <h2>Grand Child of App component - Child of ChildComponent </h2> 
        <pre>Injected username from Grandpaernt component <br/> Username: {{username}} </pre>
    </div>
</template>
<script>
export default {
    name:'GrandChildComponent',
    data(){

    },
    inject:["username"]
}
</script>
<style lang="">
    
</style>