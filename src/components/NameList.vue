<template lang="">
    <h3 v-for="name in names" :key="name.last">
        <slot :firstName="name.first"></slot>
        <slot :lastName="name.last"></slot>
    </h3>
</template>

<script>
export default {
    name: 'NameList',
    data() {
        return {
            names: [
                { first: 'Tony', last: "Stark" },
                { first: 'Bruce', last: 'Banner' },
                { first: 'Steven', last: 'Stranage' }
            ]
        }
    }
}
</script>
<style lang="">
    
</style>