<script>
	import Dialog from '$container/Dialog/Dialog.svelte';
	import { init_locales } from '$hooks/i18n';
	import { keyListener } from '$utils/listener';
	import { onMount } from 'svelte';
	import './styles.css';
	
	onMount(() => {
		window.addEventListener('keydown', keyListener);
		return () => window.removeEventListener('keydown', keyListener);
	})
	init_locales()
</script>

<Dialog />
<div class="app">
	<slot />
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
	}
</style>
