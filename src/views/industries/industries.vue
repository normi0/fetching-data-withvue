<template>
    <div>
      <h1>industries:</h1>
      <div v-for="industrie in industries" :key="industrie.id" class="industrie">
        <router-link
          :to="{
            name: 'industriesDetails',
            params: { id: industrie.id, industriesDetails: JSON.stringify(industrie) },
          }"
        >
          <h2>{{ industrie.name }}</h2>
        </router-link>
      </div>
    </div>
  </template>
  
  <script>


  export default {
    data() {
      return {
        industries: [],
      };
    },
    mounted() {
        fetch('http://localhost:3000/industries')
        .then(response => response.json())
        .then(data => this.industries = data)
        .catch(error => console.error('Error fetching industries:', error));
       },
    setup() {
      return {};
    },
  };
  </script>
  
  <style scoped>
  .industrie h2 {
    background: #f4f4f4;
    color: #144c33;
    cursor: pointer;
  }
  .industrie h2:hover {
    background: lightgray;
  }
  .industrie {
    background: #f4f4f4;
    padding: 20px;
    margin-bottom: 10px;
    border-radius: 5px;
    box-shadow: 0 5px 10px lightgray;
  }
  
  h1 {
    color: #144c33;
  }
  .industrie a {
    text-decoration: none;
  }
  </style>
  