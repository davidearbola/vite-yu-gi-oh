<script>
import CardList from "./CardList.vue";
export default {
	name: "AppMain",
	components: {
		CardList,
	},
};
</script>

<template>
	<main>
		<div class="fluid-container my_bg_orange p-5">
			<div class="bg-white p-3 row">
				<CardList />
			</div>
		</div>
	</main>
</template>

<style scoped>
.my_bg_orange {
	background-color: #d48f38;
}
</style>
