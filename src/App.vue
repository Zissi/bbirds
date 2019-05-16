<template>
  <div id="app">
    <Quiz :birds="birds" :playmode="playmode"/>
  </div>
</template>

<script>
import Quiz from './components/Quiz.vue';

export default {
  name: 'app',
  components: {
    Quiz,
  },
  data() {
    return {
      playmode: 'both',
      /* eslint-disable global-require */
      birds: [
        {
          name: 'Rotkehlchen',
          image: require('./assets/rotkehlchen.png'),
          audio: {
            fileName: require('./assets/rotkehlchen.ogg'),
            attribution: 'Vladimir Yu. Arkhipov, Arkhivov',
          },
        },
        {
          name: 'Kohlmeise',
          image: require('./assets/kohlmeise.jpg'),
          audio: {
            fileName: require('./assets/kohlmeise.ogg'),
            attribution: 'Dengis Chantal',
          },
        },
        {
          name: 'Star',
          image: require('./assets/stare.jpg'),
          audio: {
            fileName: require('./assets/star.mp3'),
            attribution: 'Bodo Sonnenburg',
          },
        },
        {
          name: 'Schwanzmeise',
          image: require('./assets/schwanzmeise.jpg'),
          audio: {
            fileName: require('./assets/schwanzmeise.mp3'),
            attribution: 'Beatrix Saadi-Varchmin',
          },
        },
        {
          name: 'Blaumeise',
          image: require('./assets/blaumeise.jpg'),
          audio: {
            fileName: require('./assets/blaumeise.ogg'),
            attribution: 'Aubrey John Williams',
          },
        },
        {
          name: 'Mauersegler',
          image: require('./assets/mauersegler.jpg'),
          audio: {
            fileName: require('./assets/mauersegler.ogg'),
            attribution: 'Jugrü',
          },
        },
        {
          name: 'Stockente',
          image: require('./assets/stockente.jpg'),
          audio: {
            fileName: require('./assets/stockente.ogg'),
            attribution: 'Jonathon Jongsma',
          },
        },
        {
          name: 'Turmfalke',
          image: require('./assets/turmfalke.jpg'),
          audio: {
            fileName: require('./assets/turmfalke.mp3'),
            attribution: 'Sonnenburg',
          },
        },
        {
          name: 'Nachtigall',
          image: require('./assets/nachtigall.jpg'),
          audio: {
            fileName: require('./assets/nachtigall.ogg'),
            attribution: 'Sonnenburg',
          },
        },
        {
          name: 'Kranich',
          image: require('./assets/kranich.jpg'),
          audio: {
            fileName: require('./assets/kranich.mp3'),
            attribution: 'Stephan Risch',
          },
        },
        {
          name: 'Feldlerche',
          image: require('./assets/feldlerche.jpg'),
          audio: {
            fileName: require('./assets/feldlerche.ogg'),
            attribution: 'Guido Gerding',
          },
        },
        {
          name: 'Amsel',
          image: require('./assets/amsel.jpg'),
          audio: {
            fileName: require('./assets/amsel.ogg'),
            attribution: 'Anton',
          },
        },
        {
          name: 'Buchfink',
          image: require('./assets/buchfink.jpg'),
          audio: {
            fileName: require('./assets/buchfink.ogg'),
            attribution: 'Herr Küppers',
          },
        },
        {
          name: 'Bachstelze',
          image: require('./assets/bachstelze.jpg'),
          audio: {
            fileName: require('./assets/bachstelze.mp3'),
            attribution: 'Herr Küppers',
          },
        },
        {
          name: 'Grünspecht',
          image: require('./assets/grünspecht.jpg'),
          audio: {
            fileName: require('./assets/grünspecht.mp3'),
            attribution: 'Marie-Lan Taÿ Pamart',
          },
        },
        {
          name: 'Buntspecht',
          image: require('./assets/buntspecht.jpg'),
          audio: {
            fileName: require('./assets/buntspecht.ogg'),
            attribution: 'Herr Küppers',
          },
        },
        {
          name: 'Mönchsgrasmücke',
          image: require('./assets/mönchsgrasmücke.jpg'),
          audio: {
            fileName: require('./assets/mönchsgrasmücke.ogg'),
            attribution: 'Aubrey John Williams ',
          },
        },
        {
          name: 'Spatz',
          image: require('./assets/spatz.jpg'),
          audio: {
            fileName: require('./assets/spatz.ogg'),
            attribution: 'Aubrey John Williams',
          },
        },
        {
          name: 'Zaunkönig',
          image: require('./assets/zaunkönig.jpg'),
          audio: {
            fileName: require('./assets/zaunkönig.mp3'),
            attribution: 'Marie-Lan Taÿ Pamart',
          },
        },
        {
          name: 'Zilpzalp',
          image: require('./assets/zilpzalp.jpg'),
          audio: {
            fileName: require('./assets/zilpzalp.ogg'),
            attribution: 'T.Voekler',
          },
        },
        {
          name: 'Blässhuhn',
          image: require('./assets/blässhuhn.jpg'),
          audio: {
            fileName: require('./assets/blässhuhn.mp3'),
            attribution: 'Jorge Leitão',
          },
        },
        {
          name: 'Höckerschwan',
          image: require('./assets/höckerschwan.jpg'),
          audio: {
            fileName: require('./assets/höckerschwan.mp3'),
            attribution: 'Stanislas Wroza',
          },
        },
      ],
      /* eslint-enable global-require */
    };
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
