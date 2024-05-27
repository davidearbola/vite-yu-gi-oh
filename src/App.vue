<script>
import AppHeader from "./components/Header/AppHeader.vue";
import AppMain from "./components/Main/AppMain.vue";
import cards from "./data/store";
export default {
	components: {
		AppHeader,
		AppMain,
	},
	data() {
		return {
			cards,
		};
	},
	mounted() {},
};
</script>

<template>
	<AppHeader />
	<AppMain />
</template>

<style scoped></style>
