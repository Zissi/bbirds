<template>
  <div class="quiz" id="quiz">
    <section class="section">
      <div class="container">
        <img alt="Vogelbild" :src="answers[solution_idx].image">
      </div>
      <div >
        <AnswerButton
          ref="answerButton"
          :answer="answers[0].name"
          :isSolution="0===this.solution_idx"
          />
        <AnswerButton
          ref="answerButton1"
          :answer="answers[1].name"
          :isSolution="1===this.solution_idx"
        />
        <AnswerButton
          ref="answerButton2"
          :answer="answers[2].name"
          :isSolution="2===this.solution_idx"
        />
        <AnswerButton
          ref="answerButton3"
          :answer="answers[3].name"
          :isSolution="3===this.solution_idx"
        />
      </div>
        <div>
          <button @click="next()" class="button is-rounded is-outlined is-medium">Next</button>
        </div>
      </section>
  </div>
</template>

<script>
// todos
// refactor button wiederholung loswerden, nicht add und remove class in answerButton
// buttons schön anordnen
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
    msg: String,
    birds: Array,
  },
  data() {
    return {
      answers: this.choices(),
      solution_idx: Math.floor(Math.random() * 4),
    };
  },
  methods: {
    next() {
      this.solution_idx = Math.floor(Math.random() * 4);
      this.answers = this.choices();
      this.$refs.answerButton.reset();
      this.$refs.answerButton1.reset();
      this.$refs.answerButton2.reset();
      this.$refs.answerButton3.reset();
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
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
img {
height:300px
}
</style>
