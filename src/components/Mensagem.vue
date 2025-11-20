<template>
    <div class="mensagem-container">
        <p>{{ msg }}</p>
    </div>
</template>

<script setup>
defineProps({
    msg: {
        type: String,
    }
});
</script>

<style scoped>
    .mensagem-container{
        color:#004085;
        background-color: #CCE5FF;
        border-radius: 5px;
        border: 2px solid #B8DAFF;
        padding: 10px;
        max-width: 400px;
        margin: 30px auto;
    }
</style>