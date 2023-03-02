<template>
    <div class="modal-overlay" @click="$emit('close')">
        <div class="modal-content">
            <slot></slot>
            <hr/>
            <button @click="$emit('close')">Close Modal</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: "ModalUI",
        emits: ['close']
    }
</script>

<style scoped>
    .modal-overlay{
        position: absolute;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        display: grid;
        justify-content: center;
        align-items: center;
        background-color: rgba(0,0,0,0.3);
    }

    .modal-content{
        background: #fff;
        min-height: 300px;
        position: relative;
        min-width: 300px;
        justify-self: center;
        padding: 20px;
        box-shadow: 0 3px 6px rgba(0,0,0,0.3);
    }
</style>