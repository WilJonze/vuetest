<script>
export default {

  data() {
    return {
      formData: {
        name: '',
        email: '',
        age: null,
      },
      isSubmitted: false,
      submittedData: {},
    };
  },

  methods: {
    submitForm(event) {
      event.preventData();
      this.isSubmitted = true;
      this.submittedData = { ...this.formData };      
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

<div v-if="isSubmitted">
  <h2>Submissions</h2>
  <div>
    <p>Name: {{ submittedData.name }}</p>
    <p>Email: {{ submittedData.email }}</p>
    <p>Age: {{ submittedData.age }}</p>
  </div>
</div>

</template>
