<script>
export default{
  name:"Question",
  props:{
    questionsAnswered:{
      type:Number
    },
    questions:{
      type:Array
    }
  }
}

</script>

<template>

 
  <div class="questions-ctr">
    <div class="progress">
      <div class="bar"></div>
      <div class="status">  {{ questionsAnswered }} out of {{ questions.length }} questions answered</div>
    </div>
    <div class="single-question" v-for="(question, qi) in questions" v-show="questionsAnswered===qi" :key="qi">
      <div class="question">{{ question.q }}</div>
      <div class="answers" v-for="answer in question.answers">
        <div class="answer">{{ answer.text }}</div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
