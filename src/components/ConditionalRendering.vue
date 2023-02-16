<template>

    <div class="container">
        <h2 v-if="num === 0">The number is zero</h2>
        <h2 v-else-if="num < 0">The number is negative</h2>
        <h2 v-else-if="num > 0">The number is positive</h2>
        <h2 v-else>Not a number</h2>

        <template v-if="display">
            <h2>Augustine</h2>
            <h2>Akwaaba Evolution</h2>
            <h2>Vue</h2>
        </template>

        <!-- This will simply toggle the css display block or none property -->
        <h2 v-show="display">Using v-show</h2>
    </div>

</template>


<script>
export default {
    name: 'ConditionalRendering',
    data() {
        return {
            num: 1,
            display: true
        }
    }
}
</script>

<style scoped>
.container {
    border: '2px solid black';
    background: 'red';
    height: 300px;
}
</style>