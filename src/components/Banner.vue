<template>
    <div id="main-banner">
        <h1>Make Your Burguer</h1>
    </div>
</template>

<script setup>

</script>

<style scoped>
    #main-banner{
        background-image: url('/public/img/burger.jpg');
        background-position: 0 -250px;
        background-size: cover;
        height: 500px;
        display: flex;
        align-items: center;
        justify-content: flex-start;
        background-repeat: no-repeat;
    }
    #main-banner h1{
        color: white;
        text-align: center;
        font-size: 3.75rem;
        background-color:#222;
        padding:20px 40px;
    }
</style>