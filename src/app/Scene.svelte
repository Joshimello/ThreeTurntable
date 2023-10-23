<script lang="ts">
  import { T } from '@threlte/core'
  import { OrbitControls, Environment, interactivity } from '@threlte/extras'

  interactivity({
    filter: (hits, state) => {
      return hits.slice(0, 1)
    }
  })

  import Render from './Render.svelte'
  import Turntable from './Turntable.svelte'
</script>

<Turntable/>

<T.DirectionalLight
  args={[0xfff0dd, 1]}
  position={[10, 10, 0]}
/>

<Environment
  path="./"
  files="kloofendal_43d_clear_puresky_1k.hdr"
/>

<T.PerspectiveCamera
  makeDefault
  position={[0, 1, 3]}>
  <OrbitControls
    enableDamping={true}
  />
</T.PerspectiveCamera>

<Render/>