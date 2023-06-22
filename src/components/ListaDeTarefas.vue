<script setup>
    const props = defineProps(['tarefas', 'numeroTarefasPendente', 'formOption'])
</script>

<template>
    <ul class="list-group mt-4">
        <li v-if="props.tarefas.length > 0" class="list-group-item" v-for="tarefa in props.tarefas">
            <input @change="evento => tarefa.finalizado = evento.target.checked" :checked="tarefa.finalizado"
                :id="tarefa.titulo" type="checkbox">
            <label :for="tarefa.titulo" class="ms-3" :class="{ done: tarefa.finalizado }">
                {{ tarefa.titulo }}
            </label>
        </li>
        <li v-else>
            <span>Não existem tarefas pendentes</span>
        </li>
    </ul>
</template>

<style scoped>
    .done {
        text-decoration: line-through;
    }
</style>