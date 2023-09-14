<script lang="ts">
	import { T, useFrame } from '@threlte/core';
	import { AmbientLight, BoxGeometry, MeshBasicMaterial } from 'three';
	import Logo from './models/Logo.svelte';
	import { Environment } from '@threlte/extras';

	let rotationY = 0;
	let rotationZ = 0;

	useFrame((_, delta) => {
		rotationY += delta * 0.5;
		rotationZ += delta * 0.5;
	});
</script>

<T.PerspectiveCamera makeDefault position={[-1.5, 0, 40]} fov={10} />
<T.Mesh rotation.x={90} rotation.y={rotationY} rotation.z={rotationZ} position.z={10}>
	<Logo scale={1} />
	<Environment files="/img/green-01.jpg" />
</T.Mesh>
<T.AmbientLight intensity={10} />
