<template>
	<div class="post">
		<div class="post__voters">
			<arrow-icon
				class="post__voters-arrow"
				:class="{ 'post__voters-vote': vote }"
			/>
			{{ voters }}
		</div>
		<div class="post__content">
			<router-link class="post__content-link" :to="`post/${slug}`">
				<h3 class="post__content-title">{{ title }}</h3>
			</router-link>
			<p class="post__content-bodyMarkdown" v-html="bodyMarkdown" />
		</div>
	</div>
</template>

<script>
import ArrowIcon from "../../assets/images/icons/arrow";

export default {
	name: "post",
	components: {
		ArrowIcon
	},
	props: {
		title: {
			type: String,
			required: true
		},
		bodyMarkdown: {
			type: String,
			default: ""
		},
		slug: {
			type: String,
			required: true
		},
		voters: {
			type: Number,
			default: 0
		},
		vote: {
			type: Boolean,
			default: false
		}
	}
};
</script>
