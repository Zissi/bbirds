<template>
  <div id="app">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/bulma/0.7.4/css/bulma.min.css">
    <section class="hero is-success">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">Bbirds – Berliner Vögel</h1>
        </div>
      </div>
    </section>
    <Quiz :birds="birds"/>
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
      message: 'Welcome to BBirds',
      /* eslint-disable global-require */
      birds: [
        { name: 'Rotkehlchen', image: require('./assets/rotkehlchen.png'), audio: { fileName: require('./assets/rotkehlchen.ogg'), attribution: 'Vladimir Yu. Arkhipov, Arkhivov' } },
        { name: 'Kohlmeise', image: require('./assets/kohlmeise.jpg'), audio: { fileName: require('./assets/kohlmeise.ogg'), attribution: 'Dengis Chantal' } },
        { name: 'Star', image: require('./assets/stare.jpg'), audio: { fileName: require('./assets/star.mp3'), attribution: 'Bodo Sonnenburg' } },
        { name: 'Schwanzmeise', image: require('./assets/schwanzmeise.jpg'), audio: { fileName: require('./assets/schwanzmeise.mp3'), attribution: 'Beatrix Saadi-Varchmin' } },
        { name: 'Blaumeise', image: require('./assets/blaumeise.jpg'), audio: { fileName: require('./assets/blaumeise.ogg'), attribution: 'Aubrey John Williams' } },
        { name: 'Mauersegler', image: require('./assets/mauersegler.jpg'), audio: { fileName: require('./assets/mauersegler.ogg'), attribution: 'Jugrü' } },
        { name: 'Stockente', image: require('./assets/stockente.jpg'), audio: { fileName: require('./assets/stockente.ogg'), attribution: 'Jonathon Jongsma' } },
        { name: 'Turmfalke', image: require('./assets/turmfalke.jpg'), audio: { fileName: require('./assets/turmfalke.mp3'), attribution: 'Sonnenburg' } },
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
