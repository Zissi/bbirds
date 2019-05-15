<template>
  <div class="quiz" id="quiz">
    <section class="section">
      <div class="container">
        <div class="vogelbild" v-if="playmode==='pictures'|| playmode === 'both'">
        <img alt="Vogelbild" :src="answers[solution_idx].image">
        </div>
        <div class="vogelsound" v-if="playmode==='sounds'|| playmode === 'both'">
        <audio controls autoplay ref="player">
          <source :src="answers[solution_idx].audio.fileName" type="audio/ogg">
          Your browser does not support the audio element.
        </audio>
        </div>

        <div class="answers-container">
          <AnswerButton
            v-for="(answer, idx) in answers"
            v-bind:key="answer.name"
            ref="answerButton"
            :answer="answer.name"
            :isSolution="idx===solution_idx"
          />
        </div>
        <div class="next-button-container">
          <button @click="next()" class="button is-rounded is-outlined is-medium">Next</button>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
// todos
// space über hero loswerden
// audio abspielen
// auswählen ob audio oder bilder
// gemischte option
// blinden gerechte alternativ texte erstellen
import AnswerButton from './AnswerButton.vue';

export default {
  name: 'Quiz',
  components: {
    AnswerButton,
  },
  props: {
    birds: Array,
    playmode: String,
  },
  data() {
    return {
      answers: this.choices(),
      solution_idx: Math.floor(Math.random() * 4),
    };
  },
  mounted() {
    this.$watch('answers', function () {
      this.$refs.player.load();
    });
  },
  methods: {
    next() {
      this.solution_idx = Math.floor(Math.random() * 4);
      this.answers = this.choices();
      for (let i = 0; i < this.$refs.answerButton.length; i += 1) {
        this.$refs.answerButton[i].reset();
      }
    },
    choices() {
      const answers = [];
      while (answers.length < 4) {
        const index = Math.floor(Math.random() * this.birds.length);
        const answer = this.birds[index];
        if (!answers.includes(answer)) {
          answers.push(answer);
        }
      }
      return answers;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
img {
  height: 300px;
}
.answers-container {
  display: flex;
  justify-content: center;
}

.next-button-container {
  padding: 10px;
}

.vogelbild{
  padding: 10px;
}

.vogelsound{
  padding: 10px;
}
</style>
