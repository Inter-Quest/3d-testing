<script lang="ts">
	//   import App from '$lib/components/App.svelte'
	import Logo_baked2 from '$lib/components/models/Logo_baked2.svelte';
	import { Canvas, T } from '@threlte/core';
	import { ContactShadows, Grid, OrbitControls } from '@threlte/extras';
</script>

<div>
	<Canvas>
		<T.PerspectiveCamera makeDefault position={[-10, 10, 10]} fov={15}>
			<OrbitControls
				autoRotate
				enableZoom={false}
				enableDamping
				autoRotateSpeed={0.5}
				target.y={1.5}
			/>
		</T.PerspectiveCamera>

		<T.DirectionalLight intensity={0.8} position.x={5} position.y={10} />
		<T.AmbientLight intensity={0.2} />

		<Grid
			position.y={-0.001}
			cellColor="#ffffff"
			sectionColor="#ffffff"
			sectionThickness={0}
			fadeDistance={25}
			cellSize={2}
		/>

		<ContactShadows scale={10} blur={2} far={2.5} opacity={0.5} />
		<!-- <T.PerspectiveCamera
			makeDefault
			position={[0, 6, 1]}
			on:create={({ ref }) => {
				ref.lookAt(0, 1, 0);
			}}
		>
			<OrbitControls enableDamping />
		</T.PerspectiveCamera> -->
		<T.DirectionalLight position={[0, 10, 3]} />

		<Logo_baked2 scale={1} position={[0, 0, 0]} />
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
