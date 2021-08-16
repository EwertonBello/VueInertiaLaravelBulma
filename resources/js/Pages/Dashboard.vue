<template>
	<h1>Dashboard {{valor}}</h1>
	<button class="button is-link" v-on:click="increment">Incrementar</button>
    <Link href="/" class="button is-warning">Voltar</Link>
</template>

<script lang="ts">
	import { defineComponent } from "vue";
	import { Link } from '@inertiajs/inertia-vue3';

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
		},
        components: {
            Link,
        }
	})
</script>
