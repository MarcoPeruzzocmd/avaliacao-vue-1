<script setup>
const model = defineModel()

const props = defineProps(['textoPreenchido']);
const emit = defineEmits(['update:textoPreenchido', 'adicionarTarefa']);


function adicionar() {
    if (props.textoPreenchido!== '') {
        emit('adicionarTarefa');
    }
}
</script>

<template>
    <section class="card">
        <h2>Adicione uma nova tarefa</h2>
        <input type="text" v-model="model" @keyup.enter="$emit('adicionarTarefa')" />
        <button @click="adicionar">Adicionar</button>
    </section>
</template>

<style scoped>
input {
    width: 50%;
    padding: 5px;
    margin: 5px 0;
}

button {
    padding: 5px;
    margin: 5px 0;
}
</style>