<template>
	<h1>Um vue aqui={{valor}}</h1>
	<button class="button is-link" v-on:click="increment">Incrementar</button>
</template>

<script lang="ts">
	import { defineComponent } from "vue";

	interface WelcomeData {
	  valor: number;
	}

	export default defineComponent({
		data(): WelcomeData {
			return {
				valor: 0
			}
		},
		methods: {
			increment(): void {
				this.valor++
			}
		}
	})
</script>
