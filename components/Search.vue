<template>
  <form @submit.prevent="onSubmit">
		<input type="text" v-model="search" placeholder="Pesquise por uma piada">

		<button type="submit">Pesquisar</button>
	</form>
</template>

<script>
export default {
	name: 'Search',

	data() {
		return {
			search: ''
		}
	},

	methods: {
		onSubmit() {
			this.$emit('search-joke', this.search);
			this.search = '';
		}
	}
}
</script>

<style scoped>
	input {
		border: 1px solid #ccc;
		outline: none;
		padding: 5px;
	}

	button {
		background: black;
		color: white;
		outline: none;
		border: 1px solid black;
		padding: 5px;
	}

	button:hover {
		background: #ccc;
    color: black;
    box-shadow: 0 0 5px black;
		cursor: pointer;
	}
</style>