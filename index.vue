<script>
import axios from 'axios'
export default {

data() {
  return {
    articles: [],
  }
},

methods: {
  async fetchHeadlines() {
    const apiKey = bc1958d801b94dadb8d528a055b87367
    const url = "https://newapi.org/v2/top-headlines?apiKey=${apiKey}"

    try {
      const response = await axios.get(url);
      this.articles = response.data.articles;
        }catch(error){
          console.error(error)
    }
    }
  },


mounted() {
  this.fetchHeadlines();
},

}


</script>

<template>
<h1>HelloWorld</h1>
<h2>Top Headlines for today</h2>
<ul>
  <li v-for="articles in articles" :key="article.title">
    <h3> {{ article.title }}</h3>
    <p> {{ article.description }}</p>
  </li>
</ul>
</template>

<style scoped>

#form-entry {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  flex-wrap:nowrap;
  flex-direction: column;
  padding: 5px;
  gap: 5px;
  }

#form-submission {
  border: 1px solid black;
}

#form-entry,
#form-submission {
  flex: 1,
}
</style>
