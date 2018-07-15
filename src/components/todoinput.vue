<template lang="pug">
	.todo-input
		input(type="text" v-model="todo.name" v-on:keydown.enter="addData").input
</template>

<script>
let uniqId = 1;
export default {
	data(){
		return {
			todo: {
				id: 0,
				name: '',
				checked: false
			}
		}
	},
	methods: {
		addData(){
			this.todo.id = uniqId++;
			this.$emit('addData', {...this.todo});
			this.todo.name = '';
		}
	}
}
</script>


<style lang="scss" src="styles/todoinput.scss">

</style>

