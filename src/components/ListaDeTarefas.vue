<script setup>
    const props = defineProps(['tarefas'])

</script>

<template>
    
    <ul class="list-group mt-4" v-if="props.tarefas.length > 0">

        <li class="list-group-item" v-for="tarefa in props.tarefas">
            <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada" :id="tarefa.titulo" type="checkbox">
        <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">
            {{ tarefa.titulo }}
        </label>
        </li>

    </ul>

    <p v-else>
        Você não possui tarefas pendentes.
    </p>
    
</template>

<style scoped>
    .done {
        text-decoration: line-through;
    }

    p {
        text-align: center;
        margin-top: 40px;
        font-size: 30px;
    } 
</style>