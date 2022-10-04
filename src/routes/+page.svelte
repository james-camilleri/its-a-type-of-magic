<script>
  import Slide from '$lib/components/layout/Slide.svelte'

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
<Slide image={PriorArt} />
<Slide image={OnJournalism2} />
<Slide image={Prototype_1} />
<Slide image={Prototype_2} />
<section
  data-background-iframe="https://stately.ai/viz/embed/71a899bf-d43a-4f95-b687-0ddaf0cc4386?mode=viz&panel=code&showOriginalLink=1&readOnly=1&pan=1&zoom=1&controls=1"
  data-background-interactive="true"
/>
<section
  data-background-iframe="https://gallery.autodesk.com/projects/172467/assets/664311/embed"
  data-background-interactive="true"
/>
<section
  data-background-iframe="https://gallery.autodesk.com/projects/172467/assets/664318/embed"
  data-background-interactive="true"
/>
<!-- <section
  data-background-iframe="https://www.masswerk.at/elizabot/eliza.html"
  data-background-interactive="true"
  /> -->
<Slide title="bloomsbury theatre" />
<Slide image={Bloomsbury} />
<Slide image={WizardOfOz} />
<Slide image={MechanicalTurk} />
<Slide image={Spotlight} />
<Slide image={EECummings} />

<Slide title="here east" />
<Slide title="london festival of architecture" />
<Slide title="TEDx goodenough college" />
<Slide title="ars electronica festival" />
<Slide title="thesis" subtitle="evina kipeni-thalassinou" />
<Slide subtitle="interactive performance" />
<Slide subtitle="co-creation" />
<Slide subtitle="the &quot;gaze&quot; of the artwork" />
<Slide subtitle="typo as therapist" />
<Slide subtitle="conclusion" />
<Slide title="next steps" />

<Slide image={Crits_1} />
<Slide image={Crits_2} />
