<script lang="ts">
	import { T, useFrame } from '@threlte/core';
	import Logo from './models/Logo.svelte';
	import { Environment } from '@threlte/extras';
	import { onMount } from 'svelte';

	let rotationY = 0;
	let rotationZ = 0;
	let rotationX = 90;

	let rotationEnabled = false;

	useFrame((_, delta) => {
		if (rotationEnabled) {
			rotationY += delta * 0.5;
			rotationZ += delta * 0.5;
		}
	});

	onMount(() => {
		document.body.prepend(controlsEle);
	});

	let controlsEle: HTMLDivElement;
</script>

<div
	bind:this={controlsEle}
	style="padding: 1rem; position: fixed; background: rgba(255,255,255,0.5); right:0;"
>
	<label>
		Enable Auto Rotate
		<input type="checkbox" bind:checked={rotationEnabled} />
	</label>
	<label>
		Rotation X
		<input type="number" min="0" max="360" step="0.1" bind:value={rotationX} />
	</label>

	<label>
		Rotation Y
		<input type="number" min="0" max="360" step="0.1" bind:value={rotationY} />
	</label>

	<label>
		Rotation Z
		<input type="number" min="0" max="360" step="0.1" bind:value={rotationZ} />
	</label>
</div>

<T.PerspectiveCamera makeDefault position={[-1.5, 0, 40]} fov={10} />
<T.Mesh rotation.x={rotationX} rotation.y={rotationY} rotation.z={rotationZ} position.z={10}>
	<Logo scale={1} />
	<Environment files="/img/green-01.jpg" />
</T.Mesh>
<T.AmbientLight intensity={10} />
