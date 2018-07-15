<template lang="pug">
	.todo
		.container
			todo-input(
				v-on:addData="addNewData"
			)
			todo-list(
				v-bind:todos="todos",
				v-on:checkTodo="checkTodo"
			)

</template>


<script>

import todoInput from './todoinput';
import todoList from './todolist';

export default {
	data() {
		return {
			todos: []
		}
	},
	methods: {
		addNewData(todo){
			this.todos.push(todo)
		},
		checkTodo(todo){
			this.todos = this.todos.map(item => item.id === todo.id ? todo : item)
		}
	},
	components: {
		todoInput,
		todoList,
	}
}
</script>

<style lang="scss" src="styles/todo.scss"></style>

