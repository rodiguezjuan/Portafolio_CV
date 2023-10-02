<template>
    <div class="container-imagen-perfil">
        <img :src=imagen_perfil class="imagen-perfil" />
    </div>
    <div>
        <button @click="incre">presionar {{ count }}</button>
    </div>

    <div>
        <form @submit.prevent="addTodo">
            <input v-model="newTodo">
            <button>Add Todo</button>
        </form>
        <ul>
            <li v-for="todo in todos" :key="todo.id">
                {{ todo.text }}
                <button @click="removeTodo(todo.id)">X</button>
            </li>
        </ul>
    </div>
</template>

<script setup lang="js">
const props = defineProps(
    {
        src: String,
    }
)

const imagen_perfil = ref(props.src);
let count = ref(0);
let contando = 0;

function incre() {
    contando = count.value + 1;
    count.value = contando;
}
// -------------------- ------------
// give each todo a unique id
let id = 0

const newTodo = ref('')
const todos = ref([
    { id: id++, text: 'Learn HTML' },
    { id: id++, text: 'Learn JavaScript' },
    { id: id++, text: 'Learn Vue' }
])

function addTodo() {
    todos.value.push({ id: id++, text: newTodo.value })
    newTodo.value = ''
}

function removeTodo(todo) {
    console.log(todos.value.filter((t) => t.id != todo))
    todos.value = todos.value.filter((t) => t !== todo)
}

</script>

<style>
.container-imagen-perfil {
    --dimension: 200px;

    width: var(--dimension);
    height: var(--dimension);

    display: flex;
    align-items: center;
    justify-content: center;

    background-repeat: no-repeat;
    background-position: center;
    border-radius: 50%;
    background-size: 100% auto;

    overflow: hidden;
}

.imagen-perfil {
    width: 100%;

    position: relative;
    top: 16px;
}
</style>