<script lang="ts">
	import Scene from '$lib/components/Scene.svelte';
	import TestScene from '$lib/components/TestScene.svelte';
	import { Canvas } from '@threlte/core';
</script>

<div>
	<Canvas>
		<!-- <Scene /> -->
		<TestScene />
	</Canvas>
</div>

<style>
	:global(body) {
		margin: 0;
	}

	div {
		width: 100vw;
		height: 100vh;
		background: rgb(13, 19, 32);
		background: linear-gradient(180deg, rgba(13, 19, 32, 1) 0%, rgba(8, 12, 21, 1) 100%);
	}
</style>
