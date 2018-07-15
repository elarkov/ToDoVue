<template lang="pug">
	.todo-item(v-bind:class="{checked : todo.checked === true}")
		label.label {{todo.name}}
			input(type="checkbox" v-on:change="checkTodo").input-toggle
			button(type="button").remove
</template>

<script>
export default {
	props: {
		todo: Object
	},
	methods: {
		checkTodo(e){
			const todoItem = {
				...this.todo,
				checked: e.target.checked
			}
			this.$emit('checkTodo', todoItem)
		}
	}
}
</script>


<style lang="scss" src="styles/todoitem.scss"></style>


