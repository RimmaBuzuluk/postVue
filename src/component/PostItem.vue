<template>
	<div class="post__block">
		<div class="post__title"><strong>Title:</strong> {{ post.title }}</div>
		<div class="post__body"><strong>Body:</strong> {{ post.body }}</div>
	</div>
	<my-button @click="$emit('remove', post)">Delete</my-button>
</template>

<script>
import MyButton from '@/component/UI/MyButton.vue';

export default {
	components: { MyButton },
	name: 'post-item',
	props: {
		post: {
			type: Object,
			required: true,
		},
	},
};
</script>
