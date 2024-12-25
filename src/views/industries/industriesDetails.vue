<template>
    <div class="industrie-details-container">
      <h2>{{ industrie.title }}</h2>
      <div class="industrie-details">
        <p><strong>Name:</strong>{{ industrie.name }}</p>
        
        <div class="skills-requirements">
          <h3>Common Roles:</h3>
          <ul>
            <li v-for="role in industrie.common_roles" :key="role">
              {{ role }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  
  export default {
    props: {
      industriesDetails: {
        type: String,
        required: true,
      },
      id: {
        type: String,
        required: true,
      },  
    },
    
    setup(props) {
      const industrie = JSON.parse(props.industriesDetails);
      return { industrie };
    },
  };
  </script>
  
  <style scoped>
  .industrie-details {
    margin: 20px;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }
  .industrie-details-container {
    margin: 20px;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }
  .industrie-description {
    margin-top: 20px;
  }
  .industrie-requirements {
    margin-top: 20px;
  }
  </style>
  