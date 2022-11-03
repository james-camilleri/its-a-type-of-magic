<script>
  import Slide from '$lib/components/layout/Slide.svelte'
  import Poem from './Poem.svelte'
  import Interaction from './Interaction.svelte'
  import VennDiagram from './VennDiagram.svelte'
  // import CodeExample from './CodeExample.svelte'

  import Ars_1 from '$assets/images/ars-1.jpg'
  import Ars_2 from '$assets/images/ars-2.jpg'
  import Ars_3 from '$assets/images/ars-3.jpg'
  import AtmosphericMemory from '$assets/images/atmospheric-memory.png'
  import Bloomsbury from '$assets/images/bloomsbury.jpg'
  import BloomsburySketch from '$assets/images/bloomsbury-sketch.png'
  import CameraFeed from '$assets/images/camera-feed.png'
  import ChassisMetal from '$assets/images/chassis-metal.jpg'
  import ChassisWood from '$assets/images/chassis-wood.jpg'
  import cmsConversation from '$assets/images/cms-conversation.png'
  import cmsQuestions from '$assets/images/cms-questions.png'
  import ConcretePoetry from '$assets/images/concrete-poetry.jpg'
  import Crits_1 from '$assets/images/crits-1.png'
  import Crits_2 from '$assets/images/crits-2.jpg'
  import DadaPoetry from '$assets/images/dada-poetry.jpg'
  import EECummings from '$assets/images/e-e-cummings.png'
  import Eliza from '$assets/images/eliza.png'
  import Equipment from '$assets/images/equipment.jpg'
  import ExquisiteCorpse from '$assets/images/exquisite-corpse.jpg'
  import Fabrication1 from '$assets/images/fabrication-1.jpg'
  import Fabrication2 from '$assets/images/fabrication-2.jpg'
  import Fabrication3 from '$assets/images/fabrication-3.jpg'
  import LFA from '$assets/images/lfa.jpg'
  import LorenCarpenterHiveMind from '$assets/images/loren-carpenter-hive-mind.jpg'
  import MechanicalTurk from '$assets/images/mechanical-turk.jpg'
  import OnJournalism2 from '$assets/images/on-journalism-2.jpg'
  import PaulSmith from '$assets/images/paul-smith.jpg'
  import PriorArt from '$assets/images/prior-art.png'
  import Prototype_1 from '$assets/images/prototype-1.jpg'
  import publicSite from '$assets/images/public-site.png'
  import Spotlight from '$assets/images/spotlight.png'
  import Summary from './Summary.svelte'
  import TedX_1 from '$assets/images/ted-x-1.jpg'
  import TedX_2 from '$assets/images/ted-x-2.jpg'
  import Theatre from '$assets/images/theatre.png'
  import Tutorial from '$assets/images/tutorial.svg'
  import TypewriterStories from '$assets/images/typewriter-stories.png'
  import TypoWithSoftware from '$assets/images/typo-with-software.jpg'
  import Wiring from '$assets/images/wiring.png'
  import WizardOfOz from '$assets/images/wizard-of-oz.png'

  import Grid from '$lib/components/layout/Grid.svelte'
  import CoverImage from './CoverImage.svelte'
</script>

<!-- Introduction -->
<Slide
  title="&nbsp;typo"
  subtitle="james camilleri & evina kipeni-thalassinou"
  large
/>
<section><Tutorial /></section>
<Summary />
<Slide image={TypoWithSoftware} />

<!-- Interaction design -->
<Slide title="interaction design" />
<Interaction />
<Slide
  iframe="https://stately.ai/viz/embed/71a899bf-d43a-4f95-b687-0ddaf0cc4386?mode=viz&panel=code&showOriginalLink=1&readOnly=1&pan=1&zoom=1&controls=1"
  caption={[
    'interaction',
    'state machine showing interaction states',
    'The entire interaction is driven by a finite state machine under the hood, which allows us to clearly see the different states the software can be in diagrammatically.',
  ]}
/>
<Slide subtitle="examples of poems created by Typo and its audience" />
<Poem
  conversation={[
    {
      question: 'Pick an animal you would like to be for a day.',
      answer: 'axolotl',
    },
    { question: 'Make a wish!', answer: 'three days of rain' },
    { question: 'Make a wish!', answer: '5 days of rain' },
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
      answer: 'waking up late',
    },
  ]}
  seeds={['unicorn', 'brown', 'late']}
  poem={'There once was a Brown Unicorn,\nWho was Late for a Date with a Rhinoceros.'}
/>
<Slide iframe="https://typo.digital/generate/poetry" />

<!-- Inspiration -->
<Slide title="inspiration" />
<Slide
  video="https://giant.gfycat.com/FearfulCoordinatedDesertpupfish.mp4"
  caption={[
    'typewriter mechanics',
    '',
    'We were fascinated by the mechanics of vintage typewriters',
  ]}
/>
<Slide
  image={Theatre}
  caption={[
    'The theatre',
    '',
    'Our first pubic exhibition of Typo was in a theatre. Similarities between typewriters and theaters generated the idea of changing the role of the audience to co-creators by giving them the chance to create their own script while they are sitting.',
  ]}
/>
<Slide
  image={LorenCarpenterHiveMind}
  caption={[
    'Loren Carpenter',
    '“Hive Mind” Experiment (1991)',
    'An excellent example of interactive theatre performance, Loren Carpenter, a computer graphics developer and researcher, created a collaborative "Pong" game that audiences successfully in a theatre. A paddle with one red and one green side was left on each seat, and the audience realized that their movement of the paddles could affect what was depicted on screen. Participants played together, with no hierarchy, in order to achieve shared common goal. The purpose of the experiment was to prove that through the help of technology, humans could live and work in harmony, with computers connecting everyone (Costuna, 2017)',
  ]}
/>
<Slide
  image={DadaPoetry}
  caption={[
    'Dadaist poetry',
    '',
    'Dada was an art movement which formed during World War I in Zurich, as a reaction to the crimes of the war. The art, poetry, and performance produced by dada artists is often satirical and nonsensical in nature and helped inspire the kind of poetry the typewriter might create.',
  ]}
/>
<Slide
  image={ExquisiteCorpse}
  contain
  caption={[
    'Exquisite corpse',
    '',
    'Another example similar to the Dada movement is the Exquisite Corpse. Exquisite Corpse is a collaborative drawing approach first used by surrealist artists to create bizarre and intuitive drawings.',
  ]}
/>
<Slide
  image={Eliza}
  caption={[
    'Eliza',
    'Joseph Weizenbaum',
    'An early chatbot simulating a Rogerian psychotherapist, and one of the first pieces of software capable of attempting the Turing Test. Relied on relatively simple internal logic, but created a convincing illusion of intelligence.',
  ]}
/>

<!-- Conceptual Approach -->
<Slide title="conceptual approach" />
<VennDiagram />
<section>
  <p>
    “Most commonly, we speak of interacting with another person, and the most
    typical form of interaction is <em>a conversation</em>. Responsiveness is
    part of interactivity, but it is not the entire story, interactivity
    requires some kind of mutual <em>responsiveness</em>.” (Smuts, 2009).
  </p>
</section>

<!-- Construction -->
<Slide title="construction" />
<Slide
  image={PriorArt}
  caption={[
    'prior art',
    'Harvey Moon, Alfredo Salazar-Caro',
    'This project used car-door lock actuators and a relay array to move the typewriter keys. We made use of the same actuators for Typo but replaced the relay array with a DMX controller.',
  ]}
/>
<Slide
  image={OnJournalism2}
  caption={[
    'prior art',
    'Julian Koschwitz',
    '"On Journalism #2 Typewriter" (1992) inspired our final chassis design.',
  ]}
/>
<Slide
  image={Prototype_1}
  caption={[
    'early prototype',
    '',
    'Section of the original wooden prototype, showing the core electronic components.',
  ]}
/>
<Slide
  image={Wiring}
  contain
  caption={[
    'early wiring diagram',
    'a wiring diagram showing the basic electronic design of the system in an earlier prototype',
  ]}
/>
<Slide caption={['chassis evolution']}>
  <Grid columns={2}>
    <img src={ChassisWood} alt="wooden chassis" />
    <img src={ChassisMetal} alt="metal chassis" />
  </Grid>
</Slide>
<Slide caption={['fabrication of metal chassis']}>
  <Grid columns={2}>
    <Grid>
      <CoverImage src={Fabrication1} />
      <CoverImage src={Fabrication2} />
    </Grid>
    <CoverImage src={Fabrication3} />
  </Grid>
</Slide>
<Slide
  image={Equipment}
  caption={['components', 'all project components ready for transportation']}
/>
<Slide
  iframe="https://gallery.autodesk.com/projects/172467/assets/664311/embed"
  caption={[
    'carriage return lever',
    '3d-printed model',
    "This extension to the typewriter's carriage return lever allowed us to activate the line feed mechanism by using a hidden stepper motor under the typewriter. This was a lot more subtle and less error-prone than our initial designs, which used a string stretched across the top of the typewriter to pull the carriage return directly.",
  ]}
/>
<Slide
  iframe="https://gallery.autodesk.com/projects/172467/assets/664318/embed"
  caption={[
    'carriage return pulley housing',
    '3d-printed model',
    'This structure houses the limit switch and bearing which is used to move the carriage every line.',
  ]}
/>
<Slide
  image={publicSite}
  caption={[
    'project website',
    '',
    'https://github.com/james-camilleri/typonline',
  ]}
/>
<!-- <Slide
  image={interactionSoftware}
  caption={[
    'interaction software',
    '',
    'https://github.com/james-camilleri/typonline',
  ]}
/> -->
<Slide
  image={cmsConversation}
  caption={[
    'database interface',
    'previous project conversations',
    'https://github.com/james-camilleri/typonline',
  ]}
/>
<Slide
  image={cmsQuestions}
  caption={[
    'database interface',
    'configuration of questions',
    'https://github.com/james-camilleri/typonline',
  ]}
/>

<!-- https://github.com/james-camilleri/typonline -->
<!-- https://github.com/james-camilleri/typewriter-dmx -->

<!-- Performances -->
<Slide title="performances" />

<Slide title="bloomsbury theatre" />
<Slide image={Bloomsbury} />
<Slide image={WizardOfOz} />
<Slide iframe="https://typo.digital/live/performance/bloomsbury" />
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
<Slide small>
  <strong>
    hello we come of from darkness shall<br />
    thank and ever be because heart death and<br />
    brown the seem the body whose not<br />
  </strong>
</Slide>

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
<Slide image={Ars_2} />
<Slide image={Ars_3} />

<Slide title="next steps" />
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

<style lang="scss">
  p {
    font-size: 1.5rem;
    text-align: left;

    em {
      color: var(--primary);
    }
  }
</style>
