<script>
import MyButton from '@/component/UI/MyButton.vue';
export default {
	components: {
		MyButton,
	},
	data() {
		return {
			post: {
				title: '',
				body: '',
			},
		};
	},
	methods: {
		createPost() {
			this.post.id = Date.now();
			this.$emit('create', this.post);
			this.post = { title: '', body: '' };
		},
	},
};
</script>
<template>
	<form @submit.prevent class="form">
		<h2>Create post</h2>

		<my-input v-model:value="post.title" placeholder="type"></my-input>
		<my-input v-model:value="post.body" placeholder="body"></my-input>
		<my-button style="align-self: flex-end" @click="createPost">Create</my-button>
	</form>
</template>
<style>
.form {
	display: flex;
	flex-direction: column;
	row-gap: 20px;
}
.input {
	font-size: 16px;
	height: 20px;
	padding: 10px;
	border: 2px solid rgb(55, 116, 129);
}
</style>
