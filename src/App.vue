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
	created() {
		axios
			.get(
				"https://db.ygoprodeck.com/api/v7/cardinfo.php?num=100&offset=0"
			)
			.then((risultato) => {
				this.store.carte = risultato.data.data;
				for (let carta of this.store.carte) {
					if (carta.archetype) {
						console.log(carta.archetype);
					}
				}
			});
	},
	mounted() {},
};
</script>

<template>
	<AppHeader />
	<AppMain />
</template>

<style scoped></style>
