<template lang="">
    <div>
        <input type="text" placeholder="enter text" :value="modelValue" @input="$emit('update:modelValue', $event.target.value)"/>
    </div>
</template>
<script>
export default {
    name: 'InputComponent',
    props:{
        modelValue: String
    }
}
</script>
<style scoped>
    input[type='text']{
        display:block;
        width: 400px;
        padding: 6px 12px;
        font-size: 14px;
        line-height:1.4;
        border: 1px solid #ccc;
        border-radius: 4px
    }
</style>