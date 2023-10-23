<script>
  import { tweened } from 'svelte/motion'
  import { quartInOut } from 'svelte/easing'
  import { onMount } from 'svelte'
  import TurntableMid from '../models/Turntable_mid.svelte'
  import TurntableLeft from '../models/Turntable_left.svelte'
  import TurntableRight from '../models/Turntable_Right.svelte'
  import TurntableArm from '../models/Turntable_arm.svelte'
  import TurntableBtn from '../models/Turntable_btn.svelte'
  import Vinyl from '../models/Vinyl.svelte'

  const tmPos = tweened([0, -3, 0], { duration: 2000, easing: quartInOut })
  const tlPos = tweened([-7, -0.5, 0], { duration: 2000, easing: quartInOut })
  const trPos = tweened([7, -0.5, 0], { duration: 2000, easing: quartInOut })
  const vPos = tweened([0, 3, 0], { duration: 2000, easing: quartInOut })
  const aPos = tweened([0, 3, 0], { duration: 2000, easing: quartInOut })
  const bPos = tweened([0, 3, 0], { duration: 2000, easing: quartInOut })

  const aRot = tweened([0, 0, 0], { duration: 2000, easing: quartInOut })

  onMount(async () => {
    await tmPos.set([0, -0.5, 0])
    tlPos.set([0, -0.5, 0])
    trPos.set([0, -0.5, 0])
    await vPos.set([0, -0.5, 0])
    aPos.set([0, -0.5, 0])
    await bPos.set([0, -0.5, 0])
    aRot.set([0, 1, 0])
  })
</script>

<TurntableMid position={$tmPos}/>
<TurntableLeft position={$tlPos}/>
<TurntableRight position={$trPos}/>
<Vinyl position={$vPos}/>
<TurntableArm position={$aPos} rotation={$aRot}/>
<TurntableBtn position={$bPos}/>