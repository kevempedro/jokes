<template>
  <div>
		<nuxt-link class="back-button" to="/jokes">Voltar</nuxt-link>

		<h2>{{ this.joke }}</h2>

		<hr />

		<small>ID da Piada: {{ $route.params.id }}</small>
	</div>
</template>

<script>
import axios from 'axios';

export default {
	name: 'JokeId',

	data() {
		return {
			joke: {}
		}
	},

	async created() {
		const config = {
			headers: {
				'Accept': 'application/json'
			}
		}

		try {
			const res = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config);

			this.joke = res.data.joke;
		} catch (err) {
			console.log('ERROR -> ', err);
		}
	}
}
</script>

<style scoped>
	.back-button {
		background: black;
		color: white;
		padding: 0.6rem;
	}

	.back-button:hover {
		background: #ccc;
		color: black;
		box-shadow: 0 0 5px black;
	}

	h2 {
		margin-top: 1.0rem;
	}
</style>