<template>
  <h2>Jobs</h2>
  <div v-if="jobs">
    <div v-for="job in jobs" :key="job.id" class="job">
     <router-link :to="{ name: 'JobDetails', params: {id: job.id} }">
        <h3>{{job.title}}</h3>
     </router-link>
  </div>
  </div>
  <div v-else>
    <p>Loading Jobs ....</p>
  </div>
</template>

<script>
export default {
    data() {
        return {
            jobs: []
        }
    },
    mounted(){
        fetch(' http://localhost:3000/jobs')
            .then(res => res.json())
            .then((data => this.jobs = data))
            .catch(err => console.log(err.message))
    }

}
</script>

<style>
    .job h3 {
        background: #f4f4f4;
        padding: 20px;
        margin: 10px auto;
        color: #444;
        cursor: pointer;
        max-width: 600px;
        border-radius: 10px;

    }
    .job h3:hover {
        background: #ddd;
    }
    .job a {
        text-decoration: none;
    }
</style>