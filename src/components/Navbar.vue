<template>
    <div id="nav">
        <router-linkc to="/" id="logo-url">
            <img :src="caminho" :alt="alt" id="logo">
        </router-linkc>
        <router-link to="/">Home</router-link>
        <router-link to="/pedidos">Pedidos</router-link>
    </div>
</template>
<script setup>
defineProps(
    {
        caminho: String,
        alt: String
    }
)
</script>

<style scoped>
    #nav{
        background-color: #222;
        border-bottom:4px solid #111;
        padding: 15px 50px;
        display: flex;
        justify-content: flex-end;
        align-items: center;
    }
    #logo-url{
        margin: auto;
        margin-left: 0;
    }
    #logo{
        width: 40px;
        height: 40px;
    }
    #nav a{
        color: #FCBA03;
        text-decoration:none;
        margin: 12px;
        transition: 0.5s;
    }
    #nav a:hover{
        color: white;
    }
</style>