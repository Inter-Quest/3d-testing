<script lang="ts">
	import { T, useFrame } from '@threlte/core';
	import Logo from './models/Logo.svelte';
	import { Environment, Grid } from '@threlte/extras';
	import { onMount } from 'svelte';

	let rotationY = 0;
	let rotationZ = 0;
	let rotationX = 90;

	let cameraPositionX = -1.5;
	let cameraPositionY = 0;
	let cameraPositionZ = 40;

	let rotationEnabled = false;

	useFrame((_, delta) => {
		if (rotationEnabled) {
			rotationY += delta * 0.5;
			rotationZ += delta * 0.5;
		}
	});

	onMount(() => {
		document.body.prepend(controlsEle);
		document.body.append(cameraControlsEle);
	});

	let controlsEle: HTMLDivElement;
	let cameraControlsEle: HTMLDivElement;
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

<div
	bind:this={cameraControlsEle}
	style="padding: 1rem; position: fixed; background: rgba(255,255,255,0.5); right:0; bottom:0 ;"
>
	<label>
		Camera Position X
		<input type="number" min="-100" max="100" step="0.1" bind:value={cameraPositionX} />
	</label>
	<label>
		Camera Position Y
		<input type="number" min="-100" max="100" step="0.1" bind:value={cameraPositionY} />
	</label>
	<label>
		Camera Position Z
		<input type="number" min="-100" max="100" step="0.1" bind:value={cameraPositionZ} />
	</label>
	<button
		on:click={() => {
			cameraPositionX = 0;
			cameraPositionY = 0;
			// cameraPositionZ = 0;
			rotationX = 0;
			rotationY = 0;
			rotationZ = 0;
		}}
	>
		Set all 0 (except camera Z)
	</button>
</div>

<T.PerspectiveCamera
	makeDefault
	position={[cameraPositionX, cameraPositionY, cameraPositionZ]}
	fov={10}
/>
<T.Mesh rotation.x={rotationX} rotation.y={rotationY} rotation.z={rotationZ} position.z={10}>
	<Logo scale={1} />
	<Environment files="/img/green-01.jpg" />
</T.Mesh>
<T.AmbientLight intensity={10} />
