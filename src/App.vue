<template>
    <Hero />
    <Results />
    <BestPractice />
    <TestYourself />
    <Faqs />
    <Resources />
</template>

<script>

import BestPractice from './components/BestPractice/BestPractice';
import Faqs from './components/Faqs/Faqs';
import Hero from './components/Hero/Hero';
import Resources from './components/Resources/Resources';
import Results from './components/Results/Results';
import TestYourself from './components/TestYourself/TestYourself';


export default {
    components: {
      Hero,
      Results,
      BestPractice,
      TestYourself,
      Faqs,
      Resources
    }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300;400&family=Oswald:wght@400;500;700&display=swap');

html { 
  scroll-behavior: smooth
}

h1 {
  text-align: center;
  font-family: $primaryFont;
  font-size: 38px;
  text-transform: uppercase;
}

h2 {
  font-family: $primaryFont;
  font-size: 28px;
  text-transform: uppercase;
}

h3 {
  font-family: Oswald, sans-serif;
  font-size: 21px;
  font-weight: 700;
  text-transform: uppercase;
}

p, ul {
  font-family: $secondaryFont;
  font-size: 14px;
  line-height: 20px;
}

#app {
  max-width: 1200px;
  display: flex;
  flex-direction: column;
  margin: 0 auto;
}
</style>