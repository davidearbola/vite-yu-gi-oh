<script>
export default {
	name: "SingleCard",
	props: { card: Object },
};
</script>

<template>
	<img :src="card.card_images[0].image_url_small" alt="" />
	<div class="py-3 my_bg_orange">
		<p>{{ card.name }}</p>
		<span class="text-dark">{{ card.archetype }}</span>
		<span class="text-dark">{{ card.attribute }}</span>
	</div>
</template>

<style scoped>
.my_bg_orange {
	background-color: #d48f38;
}
img {
	width: 100%;
	aspect-ratio: 9/16;
}

span {
	font-size: 12px;
}
</style>
