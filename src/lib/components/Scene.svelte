<script lang="ts">
	import { browser } from '$app/environment';
	import Logo from '$lib/components/models/Logo.svelte';
	import { Canvas, T, useThrelte, extend } from '@threlte/core';
	import { ContactShadows, Grid } from '@threlte/extras';
	import { onDestroy, onMount } from 'svelte';
	import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';

	extend({ OrbitControls });
	const { renderer, invalidate } = useThrelte();

	let intervalId: ReturnType<typeof setInterval>;
	onMount(() => {
		intervalId = setInterval(() => {
			// x = x + 1;
			// y = y + 1;
			// z = z + 1;
		}, 1000);
	});

	onDestroy(() => {
		clearInterval(intervalId);
	});

	let x = 0;
	let y = 6;
	let z = 0;

	let cameraLookAt = {
		x: -30,
		y: 0,
		z: 0
	};

	$: {
		console.log(cameraLookAt);
	}
	let cameraRef: any;

	function onOrbitControlsChange(e: any) {
		const target = e.target;
		const { x, y, z } = target.object.position;
		cameraLookAt = { x, y, z };
	}
</script>

<!-- <input type="range" step="0.1" min="-10" max="10" bind:value={x} />
{x}
<input type="range" step="0.1" min="-10" max="10" bind:value={y} />
{y}
<input type="range" step="0.1" min="-10" max="10" bind:value={z} />
{z}

<input type="range" step="0.1" min="-10" max="10" bind:value={cameraLookAt.x} />
{cameraLookAt.x}
<input type="range" step="0.1" min="-10" max="10" bind:value={cameraLookAt.y} />
{cameraLookAt.y}
<input type="range" step="0.1" min="-10" max="10" bind:value={cameraLookAt.z} />
{cameraLookAt.z} -->

<Logo scale={1} position={[0, 0, 0]} />
<T.PerspectiveCamera makeDefault let:ref>
	<T.OrbitControls args={[ref, renderer.domElement]} on:change={invalidate} />
</T.PerspectiveCamera>
<T.DirectionalLight intensity={0.8} position.x={5} position.y={10} />
<T.AmbientLight intensity={0.2} />

<ContactShadows scale={10} blur={2} far={2.5} opacity={0.5} />

<T.DirectionalLight position={[0, 10, 3]} />
