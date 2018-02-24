<template>
  <div id="app">
    <h1>{{title}}</h1>
    <input type="text" v-model="newItem" v-on:keyup.enter="onEnter">
    <ul>
      <li v-for = "(item,index) in items" v-bind:class="{finished:item.isFinished}" v-on:click="lifinished(item)">
        {{item.label}}
      </li>
    </ul>
    <component-a msgfrom="lzslzs"></component-a>
  </div>
</template>

<script>
import Store from './store'
import componentA from './components/componentA'
console.log(Store)
export default {
  name: "App",
  data: function() {
    return {
      title: "My First ToDoList",
      items: Store.fetch(),
      newItem: ""
    };
  },
  components:{componentA},
  watch: {
    items:{
      handler: function(items){
        Store.save(items)
      },
      deep:true
    }
  },
  methods: {
    lifinished: function(item) {
      item.isFinished = !item.isFinished;
    },
    onEnter: function() {
      this.items.push({
        label: this.newItem,
        isFinished: false
      });
      this.newItem = "";
    }
  }
};
</script>

<style lang="less">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  .finished{
    text-decoration: underline;
  }
}

</style>
