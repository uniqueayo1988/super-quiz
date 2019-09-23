<template>
  <div>
    <div class="row">
      <div class="col-xs-12 col-sm-8 offset-sm-2 col-md-6 offset-md-3">
        <h1 class="text-center">The Super Quiz</h1>
      </div>
    </div>
    <hr>
    <div class="row">
      <div class="col-xs-12 col-sm-8 offset-sm-2 col-md-6 offset-md-3">
        <component :is="mode" @answered="answered($event)" @confirmed="mode = 'Question'"></component>
      </div>
    </div>   
  </div>
</template>

<script>
import Question from './Question.vue'
import Answer from './Answer.vue'
export default {
  components: {
    Question,
    Answer
  },
  data () {
    return {
      mode: 'Question'
    }
  },
  methods: {
    answered (isCorrect) {
      if (isCorrect) {
        this.mode = 'Answer'
      } else {
        this.mode = 'Question'
        alert('Wrong, try again!')
      }
    }
  }
}
</script>

<style>

</style>
