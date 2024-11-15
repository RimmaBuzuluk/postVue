<script>
import PostItem from '@/component/PostItem.vue';
export default {
	components: { PostItem },
	props: {
		posts: {
			type: Array,
			require: true,
		},
	},
};
</script>

<template>
	<div class="posts" v-for="post in posts" :key="post.id">
		<post-item :post="post" @remove="$emit('remove', post)"></post-item>
	</div>
</template>

<style>
.posts {
	border: 2px solid rgb(55, 116, 129);
	margin-top: 10px;
	display: flex;
	justify-content: space-between;
	padding: 10px;
}
</style>
