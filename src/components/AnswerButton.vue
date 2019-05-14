<template>
  <div class="answer-button-container">
    <button
      ref="button"
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
      this.$refs.button.classList.remove('is-success');
      this.$refs.button.classList.remove('is-danger');
      this.$refs.button.classList.add('is-outlined');
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
button {
  width: 200px;
}
.answer-button-container {
  padding: 3px;
}
</style>
