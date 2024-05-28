<script>
import AppHeader from "./components/Header/AppHeader.vue";
import AppMain from "./components/Main/AppMain.vue";
import store from "./data/store.js";
import axios from "axios";

export default {
	components: {
		AppHeader,
		AppMain,
	},
	data() {
		return {
			store,
			inputValue: "",
		};
	},
	methods: {
		prova() {
			console.log(this.inputValue);
		},
	},
	created() {
		axios
			.get(
				"https://db.ygoprodeck.com/api/v7/cardinfo.php?num=100&offset=0"
			)
			.then((risultato) => {
				this.store.carte = risultato.data.data;
				// for (let carta of this.store.carte) {
				// 	if (carta.archetype) {
				// 		console.log(carta.archetype);
				// 	}
				// }
			});
		axios
			.get("https://db.ygoprodeck.com/api/v7/archetypes.php")
			.then((risultato) => {
				this.store.archetypeList = risultato.data;
			});
	},
	mounted() {},
};
</script>

<template>
	<AppHeader />
	<div class="bg-dark p-2">
		<select v-model="inputValue">
			<option value="">Trova Carta</option>
			<option v-for="archetype in store.archetypeList">
				{{ archetype.archetype_name }}
			</option>
		</select>
		<button @click="prova()">click</button>
	</div>
	<AppMain />
</template>

<style scoped></style>
