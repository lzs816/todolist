<template>
    <section class="real-app">
        <input
            type="text"
            class="add-input"
            autofocus="autofocus"
            placeholder="接下来要做什么？"
            @keyup.enter="addTodo"
        >
    </section>
</template>

<script>
export default {
    methods:{
        addTodo(){

        }
    }
}
</script>

<style lang="less" scoped>
    .real-app{
        width: 600px;
        margin: 0 auto;
        box-shadow:0 0 5px #666;
        .add-input{
            position: relative;
            margin:0;
            width: 100%;
            font-size: 24px;
            line-height: 1.4em;
            outline: none;
            padding: 6px;
            border:1px solid #999;
            box-shadow: inset 0 -1px 5px 0 rgba(0,0,0,.4);
        }
    }
</style>


