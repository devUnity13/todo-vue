<script setup>
const props = defineProps(['tarefas']);
</script>

<template>
    <ul class="list-group mt-4">
        <li v-if:="props.tarefas.length > 0" class="list-group-item" v-for="tarefa in props.tarefas">
            <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada"
                :id="tarefa.titulo" type="checkbox">
            <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">
                {{ tarefa.titulo }}
            </label>
        </li>
        <span v-else>Você não possui nenhuma tarefa, cadastre a primeira tarefa para começar!</span>
    </ul>
</template>