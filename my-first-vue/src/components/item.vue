<template>
    <div :class="['todo-item'], todo.completed ? 'cpmpleted' : ''">
        <input
            type="checkbox"
            class="toggle"
            v-model="todo.completed"
        >
        <label>{{todo.content}}</label>
        <button class="destory" @click="deleteTodo"></button>
    </div>
</template>

<script>
export default {
    props:{
        todo:{
            type:object,
            required:true
        }
    },
    methods:{
        deleteTodo(){

        }
    }
}
</script>
