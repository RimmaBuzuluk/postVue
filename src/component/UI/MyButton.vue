<script>
export default {
	name: 'my-button',
};
</script>
<template>
	<button class="button" @click="createPost"><slot></slot></button>
</template>
<style>
.button {
	background-color: white;
	border: 2px solid rgb(55, 116, 129);
	height: 40px;
	width: 80px;
	color: rgb(55, 116, 129);
	font-weight: 600;
	/* align-self: flex-end; */
}
</style>
