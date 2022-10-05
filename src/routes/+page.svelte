<script>
  import Slide from '$lib/components/layout/Slide.svelte'
  import Poem from './Poem.svelte'
  // import CodeExample from './CodeExample.svelte'

  import TypoLFA from '$assets/typo_lfa.mp4'
  import CloseUps from '$assets/close-ups.mp4'
  import Lightbulb from '$assets/lightbulb.mp4'

  import Ars_1 from '$assets/images/ars-1.jpg'
  import Ars_2 from '$assets/images/ars-2.jpg'
  import Ars_3 from '$assets/images/ars-3.jpg'
  import AtmosphericMemory from '$assets/images/atmospheric-memory.png'
  import Bloomsbury from '$assets/images/bloomsbury.jpg'
  import CameraFeed from '$assets/images/camera-feed.png'
  import ConcretePoetry from '$assets/images/concrete-poetry.jpg'
  import Crits_1 from '$assets/images/crits-1.png'
  import Crits_2 from '$assets/images/crits-2.jpg'
  import EECummings from '$assets/images/e-e-cummings.png'
  import ExquisiteCorpse from '$assets/images/exquisite-corpse.jpg'
  import EyeCatcher from '$assets/images/eye-catcher.png'
  import LFA from '$assets/images/lfa.jpg'
  import LorenCarpenterHiveMind from '$assets/images/loren-carpenter-hive-mind.jpg'
  import MechanicalTurk from '$assets/images/mechanical-turk.jpg'
  import ObliterationRoom from '$assets/images/obliteration-room.png'
  import OnJournalism2 from '$assets/images/on-journalism-2.jpg'
  import PaulSmith from '$assets/images/paul-smith.jpg'
  import PriorArt from '$assets/images/prior-art.png'
  import Prototype_1 from '$assets/images/prototype-1.jpg'
  import Prototype_2 from '$assets/images/prototype-2.jpg'
  import SonicBloom from '$assets/images/sonic-bloom.webp'
  import Spotlight from '$assets/images/spotlight.png'
  import TedX_1 from '$assets/images/ted-x-1.jpg'
  import TedX_2 from '$assets/images/ted-x-2.jpg'
  import Theatre from '$assets/images/theatre.png'
  import TheatreTypes from '$assets/images/theatre-types.png'
  import ThesisTitle from '$assets/images/thesis-title.png'
  import TypewriterStories from '$assets/images/typewriter-stories.png'
  import TypoWithSoftware from '$assets/images/typo-with-software.jpg'
  import VennDiagram from '$assets/images/venn-diagram.png'
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
<Slide image={Theatre} />
<Slide
  image={LorenCarpenterHiveMind}
  caption={['Loren Carpenter', '“Hive Mind” Experiment (1991)']}
/>
<Slide image={WhatIsDada} />
<Slide image={ExquisiteCorpse} contain caption={['Exquisite corpse']} />

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
<!-- <section
  data-background-iframe="https://gallery.autodesk.com/projects/172467/assets/664318/embed"
  data-background-interactive="true"
/> -->
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
<!-- TODO: ELIZAAAAA -->

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
<Slide image={CameraFeed} />
<Slide image={Spotlight} />
<Slide
  image={EECummings}
  caption={['e. e. cummings', 'Tulips & Chimneys (1922)']}
/>
<section>
  <p>
    <strong>
      hello we come of from darkness shall<br />
      thank and ever be because heart death and<br />
      brown the seem the body whose not<br />
    </strong>
  </p>
</section>

<Slide title="here east" />
<Slide image={Crits_1} />
<Slide image={Crits_2} />

<Slide title="london festival of architecture" />
<Slide image={LFA} />

<Slide title="TEDx goodenough college" />
<Slide image={TedX_1} />
<Slide image={TedX_2} />

<Slide title="ars electronica festival" />
<Slide image={Ars_1} contain />
<Slide video={Lightbulb} />
<Slide image={Ars_2} />
<Slide image={Ars_3} />
<Poem
  conversation={[
    {
      question: 'Pick an animal you would like to be for a day.',
      answer: 'axolotl',
    },
    { question: 'Make a wish!', answer: 'three days of rain' },
    { question: 'Make a wish!', answer: 'three days of rain' },
  ]}
  seeds={['axolotl', 'three', 'rain']}
  poem={'I sit by the window and watch\nthe rain fall in streaks\nI think of the axolotl\nand how it can regenerate\na lost limb\nI think of how we humans\nare not so different\nfrom this creature\nand how we, too,\ncan regenerate\nif we just have the will'}
/>
<Poem
  conversation={[
    { question: 'Coffee or tea?', answer: 't' },
    { question: 'What are you proud of?', answer: 'wearing glasses' },
    {
      question: 'What is the title of your favourite song?',
      answer: 'what a wonderful day',
    },
  ]}
  seeds={['t', 'wearing', 'wonderful']}
  poem={"My skin is wearing,\n wonderful wrinkles form.\nI'm still wonderful,\njust a little bit worn."}
/>
<Poem
  conversation={[
    { question: 'Make a wish!', answer: 'rainbow unicorn' },
    { question: 'What is the colour of your eyes?', answer: 'brown' },
    {
      question: 'Think of a bad habit you would like to quit.',
      answer: 'answerwaking up late',
    },
  ]}
  seeds={['unicorn', 'brown', 'late']}
  poem={'There once was a Brown Unicorn,\nWho was Late for a Date with a Rhinoceros.'}
/>
<!-- <Poem
  conversation={[
    { question: 'In which month is your birthday?', answer: ' I didn\'t even know babe like and everybody that I\'ve changed' },
    { question: 'What is the colour of your eyes?', answer: 'brown' },
    {
      question: 'Think of a bad habit you would like to quit.',
      answer: 'answerwaking up late',
    },
  ]}
  seeds={['brave', 'oven', 'finally']}
  poem={'The oven was finally brave\nAnd decided to come out of the cave\nIt had been hiding in for years\nIt was time to face its fears'}
/> -->

<Slide title="thesis" subtitle="evina kipeni-thalassinou" />
<Slide image={ThesisTitle} />
<Slide image={VennDiagram} />
<section>
  <p>This thesis aims to answer the following questions:</p>
  <p>
    <em
      >i) How do we create theatrical performances, with an electro/mechanical
      typewriter linked to a computer, as the principle actor?</em
    >
  </p>
</section>
<section>
  <p>This thesis aims to answer the following questions:</p>
  <p>
    i) How do we create theatrical performances, with an electro/mechanical
    typewriter linked to a computer, as the principle actor?
  </p>
  <p>
    <em> ii) What are the roles of the other participants?</em>
  </p>
</section>
<section>
  <p>This thesis aims to answer the following questions:</p>
  <p>
    i) How do we create theatrical performances, with an electro/mechanical
    typewriter linked to a computer, as the principle actor?
  </p>
  <p>ii) What are the roles of the other participants?</p>
  <p>
    <em
      >iii) How is the performance affected by the setting that it is placed in?</em
    >
  </p>
</section>
<Slide subtitle="interactive performance" />
<section>
  <p>
    “Most commonly, we speak of interacting with another person, and the most
    typical form of interaction is <em>a conversation</em>. Responsiveness is
    part of interactivity, but it is not the entire story, interactivity
    requires some kind of mutual <em>responsiveness</em>.” (Smuts, 2009).
  </p>
</section>
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
  contain
  image={TheatreTypes}
  caption={['Different types of theater', 'Pinterest (n.d.)']}
/>
<section>
  <p>
    <strong>
      Typo brings together the analogue and digital elements in order to foster
      the co-creation of a poetic piece.
    </strong>
  </p>
</section>

<Slide title="next steps" />
<section
  data-background-iframe="https://typo.digital/live/test/poetry"
  data-background-interactive="true"
/>
<Slide image={PaulSmith} caption={['Paul Smith']} />
<Slide
  image={ConcretePoetry}
  caption={['F. Queiroz', 'Typewriter art (2018)']}
/>
<Slide
  image={TypewriterStories}
  caption={['M. Messinger', 'Typewriter Stories (2019)']}
/>
<Slide
  image={AtmosphericMemory}
  caption={['Rafael Lozano-Hemmer', 'Atmospheric Memory (2021)']}
/>

<Slide image={TypoWithSoftware} />

<style lang="scss">
  p {
    font-size: 1.5rem;
    text-align: left;
    // white-space: pre-line;
    em {
      color: var(--primary);
    }

    strong {
      font-weight: 700;
    }
  }
</style>
