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
			linkDefault:
				"https://db.ygoprodeck.com/api/v7/cardinfo.php?num=100&offset=0",
			linkArchytypeCard:
				"https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=",
			linkArchytypeName:
				"https://db.ygoprodeck.com/api/v7/archetypes.php",
		};
	},
	methods: {
		getAxiosCard(link) {
			axios.get(link).then((risultato) => {
				this.store.carte = risultato.data.data;
			});
		},
		getAxiosArchyList(link) {
			axios.get(link).then((risultato) => {
				this.store.archetypeList = risultato.data;
			});
		},
		getCards() {
			if (this.inputValue) {
				this.getAxiosCard(this.linkArchytypeCard + this.inputValue);
			} else {
				this.getAxiosCard(this.linkDefault);
			}
		},
	},
	created() {
		this.getAxiosCard(this.linkDefault);
		this.getAxiosArchyList(this.linkArchytypeName);
	},
	mounted() {},
};
</script>

<template>
	<AppHeader />
	<div class="bg-dark p-2">
		<select v-model="inputValue" @change="getCards()">
			<option value="">Trova Carta</option>
			<option v-for="archetype in store.archetypeList">
				{{ archetype.archetype_name }}
			</option>
		</select>
		<span v-if="inputValue" class="text-white ms-3"
			>Trovate {{ store.carte.length }} carte</span
		>
	</div>
	<AppMain />
</template>

<style scoped></style>
