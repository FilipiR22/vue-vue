<template>
  <h1>
    Formulário
  </h1>
    <form @submit.prevent="adicionar">
    <input v-model.trim="novoTexto" placeholder="Digite a mensagem" />
    <button>Adicionar</button>
  </form>

  <ul v-if="estado.itens.length">
    <li v-for="m in estado.itens" :key="m.id">
      #{{ m.id }} — {{ m.texto }}
    </li>
  </ul>
  <p v-else>Lista vazia.</p>
</template>

<script setup>
  import { reactive, ref } from 'vue'

  const estado = reactive({
    nextId: 3,                    // próximo ID disponível (controle local)
    itens: [
      { id: 1, texto: 'Aprender Vue.js' },
      { id: 2, texto: 'Estudar diretivas' }
    ]
  })

  const novaTarefa = ref('')

  function adicionarTarefa() {
    if (!novaTarefa.value) return
    estado.itens.push({
      id: estado.nextId++,        // ID único garantido localmente
      texto: novaTarefa.value
    })
    novaTarefa.value = ''
  }

  function removerTarefa(id) {
    estado.itens = estado.itens.filter(t => t.id !== id)
  }
</script>

<style scoped>
form { margin: 8px 0; }
input { padding: 6px; margin-right: 6px; }
ul { margin-top: 10px; padding-left: 20px; }
li { margin-bottom: 6px; }
button { cursor: pointer; }
</style>