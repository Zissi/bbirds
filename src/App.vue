<template>
  <div id="app">
    <nav class="navbar is-success" role="navigation" aria-label="main navigation">
      <div class="navbar-brand">
        <a class="navbar-item">Bbirds – Berliner Vögel</a>
        <a
          role="button"
          class="navbar-burger burger"
          :class="{'is-active': showMenu}"
          @click="showMenu = !showMenu"
          aria-label="menu"
          aria-expanded="false"
          data-target="navbarBasicExample"
        >
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
        </a>
      </div>
      <div id="navbarBasicExample" class="navbar-menu" :class="{'is-active': showMenu}">
        <div class="navbar-start">
          <div class="navbar-item has-dropdown is-hoverable">
            <a class="navbar-link">Spielmodus</a>
            <div class="navbar-dropdown">
              <a class="navbar-item" @click="playmode='pictures'">Bilder</a>
              <a class="navbar-item" @click="playmode='sounds'">Sound</a>
              <a class="navbar-item" @click="playmode='both'">Beides</a>
            </div>
          </div>
        </div>
      </div>
    </nav>
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
      showMenu: false,
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
        {
          name: 'Nebelkrähe',
          image: require('./assets/nebelkrähe.jpg'),
          audio: {
            fileName: require('./assets/nebelkrähe.mp3'),
            attribution: 'Jorge Leitão',
          },
        },
        {
          name: 'Nebelkrähe',
          image: require('./assets/nebelkrähe.jpg'),
          audio: {
            fileName: require('./assets/nebelkrähe.mp3'),
            attribution: 'Jorge Leitão',
          },
        },
        {
          name: 'Eichelhäher',
          image: require('./assets/eichelhäher.jpg'),
          audio: {
            fileName: require('./assets/eichelhäher.ogg'),
            attribution: 'Vladimir Yu. Arkhipov, Arkhivov',
          },
        },
        {
          name: 'Elster',
          image: require('./assets/elster.jpg'),
          audio: {
            fileName: require('./assets/elster.mp3'),
            attribution: 'Lars Edenius',
          },
        },
        {
          name: 'Haubentaucher',
          image: require('./assets/haubentaucher.jpg'),
          audio: {
            fileName: require('./assets/haubentaucher.mp3'),
            attribution: 'Stein Ø. Nilsen',
          },
        },
        {
          name: 'Ringeltaube',
          image: require('./assets/ringeltaube.jpg'),
          audio: {
            fileName: require('./assets/ringeltaube.ogg'),
            attribution: 'Sleepytomcat (Jens Kraglund)',
          },
        },
        {
          name: 'Dohle',
          image: require('./assets/dohle.jpg'),
          audio: {
            fileName: require('./assets/dohle.mp3'),
            attribution: 'Jorge Leitão',
          },
        },
        {
          name: 'Eisvogel',
          image: require('./assets/eisvogel.jpg'),
          audio: {
            fileName: require('./assets/eisvogel.mp3'),
            attribution: 'Bertrand Dallet',
          },
        },
        {
          name: 'Baumläufer',
          image: require('./assets/baumläufer.jpg'),
          audio: {
            fileName: require('./assets/baumläufer.mp3'),
            attribution: 'Twan Mols',
          },
        },
        {
          name: 'Hausrotschwanz',
          image: require('./assets/hausrotschwanz.jpg'),
          audio: {
            fileName: require('./assets/hausrotschwanz.ogg'),
            attribution: 'Waithamai',
          },
        },
        {
          name: 'Graureiher',
          image: require('./assets/graureiher.jpg'),
          audio: {
            fileName: require('./assets/graureiher.mp3'),
            attribution: 'brickegickel',
          },
        },
        {
          name: 'Girlitz',
          image: require('./assets/girlitz.jpg'),
          audio: {
            fileName: require('./assets/girlitz.mp3'),
            attribution: 'Niels Poul Dreyer',
          },
        },
        {
          name: 'Lachmöwe',
          image: require('./assets/lachmöwe.jpg'),
          audio: {
            fileName: require('./assets/lachmöwe.mp3'),
            attribution: 'Aladdin',
          },
        },
      ],
      /* eslint-enable global-require */
    };
  },
};
</script>
