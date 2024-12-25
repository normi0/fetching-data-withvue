<template>
    <div class="job-details-container">
      <h2>{{ job.title }}</h2>
      <div class="job-details">
        <p><strong>category:</strong>{{ job.category }}</p>
        <p><strong>type:</strong> {{ job.type }}</p>
        <p><strong>level:</strong> {{ job.level }}</p>
        
  
        <div class="job-description">
          <p><strong>Job Description:</strong> {{ job.description }}</p>
        </div>
        <div class="skills-requirements">
          <h3>skills required:</h3>
          <ul>
            <li v-for="requirement in job.skills_required" :key="requirement">
              {{ requirement }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  
  export default {
    props: {
      jobData: {
        type: String,
        required: true,
      },
      id: {
        type: String,
        required: true,
      },  
    },
    
    setup(props) {
      const job = JSON.parse(props.jobData);
      return { job };
    },
  };
  </script>
  
  <style scoped>
  .job-details {
    margin: 20px;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }
  .job-details-container {
    margin: 20px;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }
  .job-description {
    margin-top: 20px;
  }
  .job-requirements {
    margin-top: 20px;
  }
  </style>
  