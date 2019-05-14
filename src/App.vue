<template>
  <div id="app">
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
        { name: 'Rotkehlchen', image: require('./assets/rotkehlchen.png') },
        { name: 'Kohlmeise', image: require('./assets/kohlmeise.jpg') },
        { name: 'Star', image: require('./assets/stare.jpg') },
        { name: 'Schwanzmeise', image: require('./assets/schwanzmeise.jpg') },
        { name: 'Blaumeise', image: require('./assets/blaumeise.jpg') },
        { name: 'Mauersegler', image: require('./assets/mauersegler.jpg') },
        { name: 'Stockente', image: require('./assets/stockente.jpg') },
        { name: 'Turmfalke', image: require('./assets/turmfalke.jpg') },
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
