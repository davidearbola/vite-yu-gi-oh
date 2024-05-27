<script>
import SingleCard from "./SingleCard.vue";
import cards from "../../data/store";

export default {
	name: "CardList",
	components: {
		SingleCard,
	},
	data() {
		return {
			cards,
		};
	},
};
</script>

<template>
	<div v-for="card in cards" class="col-2 text-center px-3 pb-3 text-white">
		<SingleCard :card="card" />
	</div>
</template>

<style scoped></style>
