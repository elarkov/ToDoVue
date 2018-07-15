<template lang="pug">
	.todo-list(v-if="todos.length")
		.content
			ul.list
				li.item(v-for="todo in todos")
					todo-item(
						v-bind:todo="todo"
						v-on:checkTodo="checkTodo"
					)
		.footer
			.footer-content
				.counter
					| Кол-во заданий: {{todos.length}}
				.filter
					button(type="button").footer-btn Все
					button(type="button").footer-btn Активные
					button(type="button").footer-btn Готовые
</template>

<script>

import todoItem from './todoitem'

export default {
	props: {
		todos: Array
	},
	methods: {
		checkTodo(todo){
			this.$emit('checkTodo', todo);
		}
	},
	components: {
		todoItem
	}
}
</script>


<style lang="scss" src="styles/todolist.scss"></style>

