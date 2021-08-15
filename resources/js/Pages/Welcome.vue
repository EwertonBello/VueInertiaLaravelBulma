<template>
	<h1>Um vue aqui={{valor}}</h1>
	<button class="button is-link" v-on:click="increment">Incrementar</button>
</template>

<script>
	export default {
		data() {
			return {
				valor: 0
			}
		},
		methods: {
			increment() {
				this.valor++;
			}
		}
	}
</script>
