<script>
import SingleCard from "./SingleCard.vue";
import store from "../../data/store";

export default {
	name: "CardList",
	components: {
		SingleCard,
	},
	data() {
		return {
			store,
		};
	},
};
</script>

<template>
	<div
		v-for="card in store.carte"
		class="col-2 text-center px-3 pb-3 text-white"
	>
		<SingleCard :card="card" />
	</div>
</template>

<style scoped></style>
