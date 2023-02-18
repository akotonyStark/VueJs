<template lang="">
    <div>
        <h2>First Name: {{firstName}} LastName: {{lastName}} </h2>
        <h2>Computed FullName: {{fullName}} </h2>
        <button @click="items.push({id:3, name:'Airpods', price: 179})">Add Item to Cart</button>
        <h2>Total: {{totalPrice}}</h2>
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
                    price: 999
                }
            ]
        }
    },

    methods:{

    },
    computed: {
        fullName(){
            return `${this.firstName} ${this.lastName}`
        },
        totalPrice(){
            return this.items.reduce((total, item) => total = total + item.price, 0)
        }

    }
}
</script>
<style lang="">
    
</style>