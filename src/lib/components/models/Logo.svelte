<!--
Auto-generated by: https://github.com/threlte/threlte/tree/main/packages/gltf
Command: npx @threlte/gltf@1.0.1 /Users/mattschwartz/Downloads/3d-test/static/models/logo_simplified_512.glb --root /models/ --types --printwidth 120 --precision 2
-->

<script lang="ts">
  import type * as THREE from 'three'
  import { Group } from 'three'
  import { T, type Props, type Events, type Slots, forwardEventHandlers } from '@threlte/core'
  import { useGltf } from '@threlte/extras'

  type $$Props = Props<THREE.Group>
  type $$Events = Events<THREE.Group>
  type $$Slots = Slots<THREE.Group> & { fallback: {}; error: { error: any } }

  export const ref = new Group()

  type GLTFResult = {
    nodes: {
      Health: THREE.Mesh
      body: THREE.Mesh
      bolt1: THREE.Mesh
      bolt2: THREE.Mesh
      bolt3: THREE.Mesh
      bolt4: THREE.Mesh
      tail: THREE.Mesh
      eye: THREE.Mesh
      crest: THREE.Mesh
      box: THREE.Mesh
      bolt10: THREE.Mesh
      bolt11: THREE.Mesh
      bolt12: THREE.Mesh
      bolt5: THREE.Mesh
      bolt6: THREE.Mesh
      bolt7: THREE.Mesh
      bolt8: THREE.Mesh
      bolt9: THREE.Mesh
      hub: THREE.Mesh
      pin1: THREE.Mesh
      pin2: THREE.Mesh
      pin3: THREE.Mesh
      pin4: THREE.Mesh
      Plate: THREE.Mesh
    }
    materials: {
      ['Material.001']: THREE.MeshStandardMaterial
      ['BlackMetal.001']: THREE.MeshStandardMaterial
      MetalBolt: THREE.MeshStandardMaterial
      ['BlackMetal.002']: THREE.MeshStandardMaterial
      BlackMetal: THREE.MeshStandardMaterial
      ['BlackMetal.003']: THREE.MeshStandardMaterial
      PinGlow: THREE.MeshStandardMaterial
      Wheel: THREE.MeshStandardMaterial
      BlackMetal2: THREE.MeshStandardMaterial
    }
  }

  const gltf = useGltf<GLTFResult>('/models/logo_simplified_512.glb')

  const component = forwardEventHandlers()
</script>

<T is={ref} dispose={false} {...$$restProps} bind:this={$component}>
  {#await gltf}
    <slot name="fallback" />
  {:then gltf}
    <T.Mesh
      geometry={gltf.nodes.Health.geometry}
      material={gltf.materials['Material.001']}
      position={[-2.01, 0.3, -0.22]}
    />
    <T.Mesh geometry={gltf.nodes.body.geometry} material={gltf.materials['BlackMetal.001']} position={[0, 0.33, 0]} />
    <T.Mesh
      geometry={gltf.nodes.bolt1.geometry}
      material={gltf.materials.MetalBolt}
      position={[-6.23, 0.35, 3.46]}
      scale={28.08}
    />
    <T.Mesh
      geometry={gltf.nodes.bolt2.geometry}
      material={gltf.materials.MetalBolt}
      position={[-6.23, 0.35, 3.46]}
      scale={28.08}
    />
    <T.Mesh
      geometry={gltf.nodes.bolt3.geometry}
      material={gltf.materials.MetalBolt}
      position={[-6.23, 0.35, 3.46]}
      scale={28.08}
    />
    <T.Mesh
      geometry={gltf.nodes.bolt4.geometry}
      material={gltf.materials.MetalBolt}
      position={[-6.23, 0.35, 3.46]}
      scale={28.08}
    />
    <T.Mesh geometry={gltf.nodes.tail.geometry} material={gltf.materials['BlackMetal.002']} position={[0, 0.33, 0]} />
    <T.Mesh
      geometry={gltf.nodes.eye.geometry}
      material={gltf.materials['Material.001']}
      position={[-6.23, 0.34, 3.46]}
      scale={28.08}
    />
    <T.Mesh geometry={gltf.nodes.crest.geometry} material={gltf.materials.BlackMetal} position={[0, 0.33, 0]} />
    <T.Mesh geometry={gltf.nodes.box.geometry} material={gltf.materials['BlackMetal.003']} scale={[1, 0.67, 1]}>
      <T.Mesh
        geometry={gltf.nodes.bolt10.geometry}
        material={gltf.materials.PinGlow}
        position={[-6.23, 0.02, 3.46]}
        scale={28.08}
      />
      <T.Mesh
        geometry={gltf.nodes.bolt11.geometry}
        material={gltf.materials.PinGlow}
        position={[-6.23, 0.02, 3.46]}
        scale={28.08}
      />
      <T.Mesh
        geometry={gltf.nodes.bolt12.geometry}
        material={gltf.materials.PinGlow}
        position={[-6.23, 0.02, 3.46]}
        scale={28.08}
      />
      <T.Mesh
        geometry={gltf.nodes.bolt5.geometry}
        material={gltf.materials.PinGlow}
        position={[-6.23, 0.02, 3.46]}
        scale={28.08}
      />
      <T.Mesh
        geometry={gltf.nodes.bolt6.geometry}
        material={gltf.materials.PinGlow}
        position={[-6.23, 0.02, 3.46]}
        scale={28.08}
      />
      <T.Mesh
        geometry={gltf.nodes.bolt7.geometry}
        material={gltf.materials.PinGlow}
        position={[-6.23, 0.02, 3.46]}
        scale={28.08}
      />
      <T.Mesh
        geometry={gltf.nodes.bolt8.geometry}
        material={gltf.materials.PinGlow}
        position={[-6.23, 0.02, 3.46]}
        scale={28.08}
      />
      <T.Mesh
        geometry={gltf.nodes.bolt9.geometry}
        material={gltf.materials.PinGlow}
        position={[-6.23, 0.02, 3.46]}
        scale={28.08}
      />
      <T.Mesh geometry={gltf.nodes.hub.geometry} material={gltf.materials.Wheel} position={[-1.22, 0, 0.04]} />
      <T.Mesh
        geometry={gltf.nodes.pin1.geometry}
        material={gltf.materials.PinGlow}
        position={[-6.23, 0, 3.46]}
        scale={28.08}
      />
      <T.Mesh
        geometry={gltf.nodes.pin2.geometry}
        material={gltf.materials.PinGlow}
        position={[-6.23, 0, 3.46]}
        scale={28.08}
      />
      <T.Mesh
        geometry={gltf.nodes.pin3.geometry}
        material={gltf.materials.PinGlow}
        position={[-6.23, 0, 3.46]}
        scale={28.08}
      />
      <T.Mesh
        geometry={gltf.nodes.pin4.geometry}
        material={gltf.materials.PinGlow}
        position={[-6.23, 0, 3.46]}
        scale={28.08}
      />
      <T.Mesh
        geometry={gltf.nodes.Plate.geometry}
        material={gltf.materials.BlackMetal2}
        position={[-1.22, -0.29, 0.04]}
        scale={[0.62, 0.31, 0.62]}
      />
    </T.Mesh>
  {:catch error}
    <slot name="error" {error} />
  {/await}

  <slot {ref} />
</T>
