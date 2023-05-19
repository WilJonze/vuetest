<script>
export default {

  data() {
    return {
      formData: {
        name: '',
        email: '',
        age: null,
      },

      questionnaire: [
        {
        text: "Question",
        options: ["Yes" , "No", "Maybe"],
        answer: ''
        },
        {
        text: "Question",
        options: ["Yes" , "No", "Maybe"],
        answer: ''
        },
        {
        text: "Question",
        options: ["Yes" , "No", "Maybe"],
        answer: ''
        },
        {
        text: "Question",
        options: ["Yes" , "No", "Maybe"],
        answer: ''
        }
      ],
      surveyData: []
    };
  },

  methods: {
    submitForm() {
      this.formData = {
        name: '',
        email: '',
        age: null,
      };
    },

    submitSurvey(){
      this.surveyData
    },

    mounted() {
      this.surveyData = this.question.map(map => ({
        answer: ''
      }));
    }

  },
}


</script>

<template>
<h1>HelloWorld</h1>
<div>
  <h2>Form</h2>
  <form @submit="submitForm">
    <label for="name">Name:</label>
    <input type="text" id="name" v-model="formData.name" required>

    <label for="email">Email:</label>
    <input type="text" id="email" v-model="formData.email" required>

    <label for="age">Age:</label>
    <input type="text" id="age" v-model="formData.age" requried>

    <button type="submit">Submit</button>
  </form>
</div>

<div>
  <h2>Survey</h2>
  <form @submit="submitSurvey">
    <div v-for="(question, index) in questionnaire" :key="index">
      <h3>{{ question.text }}</h3>
      <div>
      <label v-for="(option, optionIndex) in question.options" :key="optionIndex">
        <input type="radio" :id="`option-${index}-${optionIndex}`" :value="option" v-model="surveyData[index].answer" required>
        {{ option }}
      </label>
    </div>
    </div>
      <button type="submit">Submit</button>
  </form>  
</div>

</template>

<style scoped>

</style>
