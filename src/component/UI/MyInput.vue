<script>
export default {
	name: 'my-input',
	props: {
		value: [String, Number],
	},
	methods: {
		updateInput(event) {
			this.$emit('update:value', event.target.value);
		},
	},
};
</script>

<template>
	<input :value="value" @input="updateInput" class="input" type="text" />
</template>

<style>
.input {
	font-size: 16px;
	height: 20px;
	padding: 10px;
	border: 2px solid rgb(55, 116, 129);
}
</style>
