<template>
    <form id="burguer-form" @submit.prevent="aqui">
        <div class="input-container">
            <label for="nome">Nome do cliente</label>
            <input type="text" id="nome" name="nome" v-model="nome" placeholder="Digite seu nome" value="olaa">
        </div>
        <div class="input-container">
            <label for="pao">Escolha o pão:</label>
            <select name="pao" id="pao" v-model="pao">
                <option value="">Selecione o seu pão</option>
                <option value="integral">Integral</option>
            </select>
        </div>
        <div class="input-container">
            <label for="carne">Escolha a carne do seu burguer:</label>
            <select name="carne" id="carne" v-model="carne">
                <option value="">Selecione a sua carne</option>
                <option value="maminha">Maminha</option>
            </select>
        </div>
        <div class="input-container">
            <label for="opcionais">Selecione os opicionais:</label>
            <div class="checkbox-container">
                <input type="checkbox" name="opcionais" v-model="opcionais" value="salame">
                <span>Salame</span>
            </div>
        </div>
        <div class="input-container">
            <input type="submit" value="Enviar Pedido">
        </div>
    </form>
</template>
<script setup>
    import { ref } from 'vue';
    const nome = ref('ola');
    const pao = ref('integral');
    const carne = ref('maminha');
    const opcionais = ref(['salame']);
    function aqui(){
        if(!nome.value || !pao.value || !carne.value || opcionais.value===' '){
            alert('Por favor, preencha todos os campos obrigatórios.');
            return;
        }
        console.log('Nome:', nome.value);
        console.log('Pão:', pao.value);
        console.log('Carne:', carne.value);
        console.log('Opcionais:', opcionais.value);
    }
</script>