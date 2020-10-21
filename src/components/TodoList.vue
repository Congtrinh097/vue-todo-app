<template>
  <div>
    <input style="width: 200px; display: block; margin: 10px 10px 10px 30px" v-model="text" v-on:keyup.enter="add" />
    <button class="button-add" type="button" v-on:click="add">Add to list!</button>
    <ul>
        <li v-for="todo in todos" 
        v-bind:key='todo.title' 
        class="normal" 
        :class="{ 'mark-done': todo.done}" 
        v-on:click="done(todo)"> 
          {{todo.title}} 
          <button class="button-remove" v-on:click="remove(todo)">Remove</button>
        </li> 
    </ul> 
  </div>
</template>

<script type = "text/javascript" >

export default {
  name: 'TodoList',
  methods: {
    done: function(todo)  {
      todo.done = !todo.done;
    },
    add : function() {
      if (this.text == "" || this.text == null) {
        return;
      }
      let newtodo = {
        title: this.text,
        project: 'Project A',
        done: false
      };
      this.todos.push(newtodo);
      this.text = "";
    },
     remove : function(item) {
      let index = this.todos.findIndex(i => i.title == item.title && i.project == item.project && i.done == item.done);
      if(index > -1) {
        this.todos.splice(index,1);
      }
    }
  },
  data() {
    return {
      text: "Todo task",
      todos: [{
        title: 'Todo A',
        project: 'Project A',
        done: false,
      }, {
        title: 'Todo B',
        project: 'Project B',
        done: true,
      }, {
        title: 'Todo C',
        project: 'Project C',
        done: false,
      }, {
        title: 'Todo D',
        project: 'Project D',
        done: false,
      }],
    };
  },
};
</script>
<style>
  .normal {
    padding: 10px;
    margin-top: 5px;
    color: red;
    background-color: gray;
    margin: 5px 30px 5px 30px;
  }
  .mark-done {
    color: green;
    background-color: rosybrown;
    list-style-type: square;
  }
  .red:active {
    background-color: green;
  }
  .button-add {
    margin-left: 30px;
    display: block;
    width: 100px;
    height: 25px;
  }
  .button-remove {
    float: right;
  }
</style>
