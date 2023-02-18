<template lang="">
    <div>
        <h2>First Name: {{firstName}} LastName: {{lastName}} </h2>
        <h2>Computed FullName: {{fullName}} </h2>
        <button @click="items.push({id:3, name:'Airpods', price: 179})">Add Item to Cart</button>
        <h2>Computed Total: {{totalPrice}}</h2>
        <h2>Method Total: {{getTotal()}}</h2>
        
        <template v-for="item in items">
            <h3 v-if="item.price > 1000" :key="item.id">{{item.name}}</h3>
        </template>
        <h3 v-for="item in inexpensiveItems" :key="item.id">{{item.name}}</h3>
    </div>
</template>
<script>
export default {
    name:'ComputedProperties',
    data(){
        return{
            firstName: 'Tony',
            lastName: 'Stark',
            items: [
                {
                    id: 1,
                    name: 'iPhone 12',
                    price: 899
                },
                {
                    id:2,
                    name: 'MacBook Air M1',
                    price: 1099
                },
                {
                    id:3,
                    name: 'MacBook Air M2',
                    price: 1299
                }
            ]
        }
    },

    methods:{
        getTotal(){
            return this.items.reduce((total, item) => total = total + item.price, 0)
        }
    },
    computed: {
        fullName(){
            return `${this.firstName} ${this.lastName}`
        },
        totalPrice(){
            return this.items.reduce((total, item) => total = total + item.price, 0)
        },
        inexpensiveItems(){
            return this.items.filter(item => item.price < 1000) 
        }

    }
}
</script>
<style lang="">
    
</style>