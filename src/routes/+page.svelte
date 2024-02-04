<script lang="ts">
	import * as THREE from 'three';
	import * as SC from 'svelte-cubed';
  const tip_width = 0.635 /2;
  const longsword_blade_length = 10.0;
</script>

<SC.Canvas
	antialias
	fog={new THREE.FogExp2('papayawhip', 0.01)}
	background={new THREE.Color('papayawhip')}
	shadows
>
	<!-- <SC.Group position={[0, -1 / 2, 0]}>
		<SC.Mesh
			geometry={new THREE.PlaneGeometry(50, 50)}
			material={new THREE.MeshStandardMaterial({ color: 'burlywood' })}
			rotation={[-Math.PI / 2, 0, 0]}
			receiveShadow
		/>

		<SC.Primitive
			object={new THREE.GridHelper(50, 50, 0x444444, 0x555555)}
			position={[0, 0.001, 0]}
		/>
	</SC.Group> -->

  <SC.Group position={[0, 5, 0]}>
    <SC.Mesh
      geometry={new THREE.CylinderGeometry(tip_width, tip_width, longsword_blade_length)}
      material={new THREE.MeshStandardMaterial({ color: 0xff3e00 })}
    />
  </SC.Group>
	
	<SC.PerspectiveCamera position={[1, 1, 3]} />
	<SC.OrbitControls enableZoom={true} /> 

	<SC.AmbientLight intensity={0.6} />
	<SC.DirectionalLight intensity={0.6} position={[-2, 3, 2]} shadow={{ mapSize: [2048, 2048] }} />
	​</SC.Canvas
>
