<script>
import AppHeader from "./components/Header/AppHeader.vue";
import AppMain from "./components/Main/AppMain.vue";
import store from "./data/store.js";
export default {
	components: {
		AppHeader,
		AppMain,
	},
	data() {
		return {
			store,
		};
	},
	created() {},
	mounted() {
		axios
			.get(
				"https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0"
			)
			.then((risultato) => {
				this.store.carte = risultato.data.data;
			});
	},
};
</script>

<template>
	<AppHeader />
	<AppMain />
</template>

<style scoped></style>
