<script>
import PostForm from '@/component/PostForm.vue';
import PostList from '@/component/PostList.vue';

export default {
	components: {
		PostForm,
		PostList,
	},
	data() {
		return {
			posts: [
				{ id: 1, title: 'js', body: 'js fflfllf' },
				{ id: 2, title: 'html', body: 'html content' },
				{ id: 3, title: 'css', body: 'css styles' },
				{ id: 4, title: 'vue', body: 'vue framework' },
			],
			title: '',
			body: '',
		};
	},
	methods: {
		createPost(post) {
			if (post.title && post.body) {
				this.posts.push(post);
			}
		},
		deletePost(post) {
			this.posts = this.posts.filter(postItem => postItem.id !== post.id);
		},
	},
};
</script>

<template>
	<div class="App">
		<PostForm @create="createPost" />
		<PostList v-if="posts.length > 0" :posts="posts" @remove="deletePost" />
		<p v-else style="color: red; font-size: 24px">You don`t have any post</p>
	</div>
</template>

<style>
* {
	margin: 0;
	padding: 0;
}

.App {
	max-width: 1200px;
	margin: 0 auto;
	padding: 10px;
	color: rgb(55, 116, 129);
}
</style>
