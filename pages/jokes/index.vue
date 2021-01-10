<template>
	<div>
		<Search v-on:search-joke="searchJoke" />

		<Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke" />
	</div>
</template>

<script>
import axios from 'axios';
import Joke from '../../components/Joke';
import Search from '../../components/Search';

export default {
	name: 'Jokes',

	components: {
		Joke,
		Search
	},

  data() {
		return {
			config: {
				headers: {
					'Accept': 'application/json'
				}
			},
			jokes: []
		}

		const config = {
			headers: {
				'Accept': 'application/json'
			}
		}
	},

	async created() {
		try {
			const res = await axios.get('https://icanhazdadjoke.com/search', this.config);

			this.jokes = res.data.results;
		} catch (err) {
			console.log('ERROR -> ', err);
		}
	},

	methods: {
		async searchJoke(search) {
			try {
				const res = await axios.get(`https://icanhazdadjoke.com/search?term=${search}`, this.config);

				this.jokes = res.data.results;
			} catch (err) {
				console.log('ERROR -> ', err);
			}
		}
	}
}
</script>

<style scoped>

</style>