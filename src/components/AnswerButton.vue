<template>
  <div class="answer-button" id="quiz">
    <button
      ref="answerButton"
      class="button is-info is-light is-outlined is-medium is-rounded"
      @click="check"
    >{{answer}}</button>
  </div>
</template>

<script>
export default {
  name: 'AnswerButton',
  props: {
    answer: String,
    isSolution: Boolean,
  },
  methods: {
    check(event) {
      if (this.isSolution) {
        event.target.classList.add('is-success');
        event.target.classList.remove('is-outlined');
      } else {
        event.target.classList.remove('is-outlined');
        event.target.classList.add('is-danger');
      }
    },
    reset() {
      this.$refs.answerButton.classList.remove('is-success');
      this.$refs.answerButton.classList.remove('is-danger');
      this.$refs.answerButton.classList.add('is-outlined');
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
button {
  width: 200px;
}
</style>
