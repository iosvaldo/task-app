    <script setup>
    import {defineEmits, reactive } from "vue";
    import TodoButton from "./TodoButton.vue"
    const emit = defineEmits(['create-todo']);

    const todoState = reactive({ 
      todo: "",
      invalid: null,
      errMsg:"",
    });

    const createTodo = () => { 
      todoState.invalid = null;
      if (todoState.todo !== "") {
        emit('create-todo', todoState.todo);
        todoState.todo = "";
        return;
      }
      todoState.invalid = true;
      todoState.errMsg = "todo value cannot be empty";
    };
    </script>
<template>
  <div class="input-wrap" :class="{ 'input-err' : todoState.invalid }">
<input placeholder="enter a task... " type="text" v-model="todoState.todo"/>

</div>
<TodoButton @click="createTodo()"/>
  <p v-show="todoState.invalid" class="err-msg">{{todoState.errMsg }}</p>
</template>


<style lang="scss" scoped>
.input-wrap {
  display: flex;
  transition: 250ms ease;
  border-radius: 1em;
  border: 2px solid #2eaae4;
    &.input-err {
    border-color: red;
  }
  &:focus-within {
    box-shadow: 0 -4px 6px -1px rgb(0 0 0 / 0.1),
      0 -2px 4px -2px rgb(0 0 0 / 0.1);
  }
  input {
    width: 100%;
    border-radius: 1.5em;
    padding: 8px 6px;
    border: none;
    &:focus {
      outline: none;
    }
  }
}

@media screen and (max-width:425px){
 .input-wrap {
  display: flex;
  transition: 250ms ease;
  border-radius: 1em;
  border: 2px solid #2eaae4;
    &.input-err {
    border-color: red;
  }
  &:focus-within {
    box-shadow: 0 -4px 6px -1px rgb(0 0 0 / 0.1),
      0 -2px 4px -2px rgb(0 0 0 / 0.1);
  }
  input {
    width: 100%;
    border-radius: 1.5em;
    padding: 8px 6px;
    border: none;
    &:focus {
      outline: none;
    }
  }
}
}

.err-msg {
  margin-top: 6px;
  font-size: 12px;
  text-align: center;
  color: red;
}
</style>