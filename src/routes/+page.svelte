<script>
  import Slide from '$lib/components/layout/Slide.svelte'
  import CodeExample from './CodeExample.svelte'

  import TypoLFA from '$assets/typo_lfa.mp4'
  import CloseUps from '$assets/close-ups.mp4'

  import Bloomsbury from '$assets/images/bloomsbury.jpg'
  import Crits_1 from '$assets/images/crits-1.png'
  import Crits_2 from '$assets/images/crits-2.jpg'
  import EECummings from '$assets/images/e-e-cummings.png'
  import ExquisiteCorpse from '$assets/images/exquisite-corpse.jpg'
  import LorenCarpenterHiveMind from '$assets/images/loren-carpenter-hive-mind.jpg'
  import MechanicalTurk from '$assets/images/mechanical-turk.jpg'
  import OnJournalism2 from '$assets/images/on-journalism-2.jpg'
  import PriorArt from '$assets/images/prior-art.png'
  import Prototype_1 from '$assets/images/prototype-1.jpg'
  import Prototype_2 from '$assets/images/prototype-2.jpg'
  import Spotlight from '$assets/images/spotlight.png'
  import WhatIsDada from '$assets/images/what-is-dada.jpg'
  import WizardOfOz from '$assets/images/wizard-of-oz.png'
  import LFA from '$assets/images/lfa.jpg'
  import SonicBloom from '$assets/images/sonic-bloom.webp'
  import TedX from '$assets/images/ted-x.jpg'
  import TheatreTypes from '$assets/images/theatre-types.png'
  import TypoWithSoftware from '$assets/images/typo-with-software.jpg'
  import EyeCatcher from '$assets/images/eye-catcher.png'
  import ObliterationRoom from '$assets/images/obliteration-room.png'
</script>

<section data-background-color="black" />
<Slide
  title="typo"
  subtitle="james camilleri & evina kipeni-thalassinou"
  large
/>
<Slide video={TypoLFA} />

<Slide title="concept" />
<Slide
  image={LorenCarpenterHiveMind}
  caption={['Loren Carpenter', '“Hive Mind” Experiment (1991)']}
/>
<Slide image={WhatIsDada} />
<Slide image={ExquisiteCorpse} contain />

<Slide title="construction" />
<Slide video={CloseUps} loop={true} />
<Slide image={PriorArt} caption={['Harvey Moon, Alfredo Salazar-Caro']} />
<Slide
  image={OnJournalism2}
  caption={['Julian Koschwitz', '"On Journalism #2 Typewriter" (1992)']}
/>
<Slide image={Prototype_1} />
<!-- <Slide image={Prototype_2} /> -->
<section
  data-background-iframe="https://gallery.autodesk.com/projects/172467/assets/664311/embed"
  data-background-interactive="true"
/>
<section
  data-background-iframe="https://gallery.autodesk.com/projects/172467/assets/664318/embed"
  data-background-interactive="true"
/>
<section
  data-background-iframe="https://stately.ai/viz/embed/71a899bf-d43a-4f95-b687-0ddaf0cc4386?mode=viz&panel=code&showOriginalLink=1&readOnly=1&pan=1&zoom=1&controls=1"
  data-background-interactive="true"
/>
<!-- TODO: Get the code in somehow. -->
<!-- <CodeExample /> -->
<!-- <section
  data-background-iframe="https://github.com/james-camilleri/typewriter-dmx/blob/main/index.ts"
  data-background-interactive="true"
/> -->
<!-- <section
  data-background-iframe="https://www.masswerk.at/elizabot/eliza.html"
  data-background-interactive="true"
  /> -->
<Slide title="bloomsbury theatre" />
<Slide image={Bloomsbury} />
<Slide image={WizardOfOz} />
<section
  data-background-iframe="https://typo.digital/live/performance/bloomsbury"
  data-background-interactive="true"
/>
<Slide
  image={MechanicalTurk}
  caption={['Mechanical Turk or Automaton Chess Player', '(18th century)']}
/>
<Slide image={Spotlight} />
<Slide
  image={EECummings}
  caption={['e. e. cummings', 'Tulips & Chimneys (1922)']}
/>

<Slide title="here east" />
<Slide image={Crits_1} />
<Slide image={Crits_2} />

<Slide title="london festival of architecture" />
<Slide image={LFA} />

<Slide title="TEDx goodenough college" />
<Slide image={TedX} />

<Slide title="ars electronica festival" />
<Slide title="thesis" subtitle="evina kipeni-thalassinou" />
<Slide subtitle="interactive performance" />
<Slide subtitle="co-creation" />
<Slide
  contain
  image={ObliterationRoom}
  caption={['Yayoi Kusama', 'Obliteration room']}
/>
<Slide subtitle="the &quot;gaze&quot; of the artwork" />
<Slide
  image={EyeCatcher}
  caption={['(Charlie) Zhang Lin', 'Eye Catcher (2014)']}
/>
<Slide subtitle="typo as therapist" />
<Slide image={SonicBloom} caption={['Yuri Suzuki', 'Sonic Bloom (2022)']} />
<Slide subtitle="conclusion" />
<Slide
  image={TheatreTypes}
  caption={['Different types of theater', 'Pinterest (n.d.)']}
/>

<Slide title="next steps" />
<section
  data-background-iframe="https://typo.digital/live/test/poetry"
  data-background-interactive="true"
/>
<Slide image={TypoWithSoftware} />
<!--
caption={['Paul Smith']}
caption={['F. Queiroz', 'Typewriter art (2018)']}
caption={['M. Messinger', 'Typewriter Stories (2019)']}
caption={['Rafael Lozano-Hemmer', 'Atmospheric Memory (2021)']} -->
