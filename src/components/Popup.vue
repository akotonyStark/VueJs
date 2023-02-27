<template lang="">
    <div>
        <h2>This is a Popup</h2>
        <input type='text' v-model="name"/>
        <button @click="$emit('close', name)">Close Popup</button>
    </div>
</template>
<script>
export default {
    name:'PopupComponent',
    emits:['close'],
    data(){
        return{
            name: ''
        }
    }
}
</script>
<style lang="">
    
</style>