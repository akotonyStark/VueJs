<template>
    <h2>{{ 2+4+8 }}</h2>
    <h2>Add Method - {{ addNumbers(4,6) }}</h2>
    <h2>Add With Inc Method - {{ addWithIncrement(4,6) + num2}}</h2>
</template>


<script>
export default{
    name:'UsingFucntions',
    data(){
        return{
            num1 : 1,
            num2 : 2
        }
    },

    methods : {
        addNumbers(a, b){
            return a + b
        },
        addWithIncrement(a,b){
            return a+b+this.num1
        }
    }
}
</script>