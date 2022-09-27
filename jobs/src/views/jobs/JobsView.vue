<template>
  <h2>Jobs</h2>
  <div v-for="job in jobs" :key="job.id" class="job">
     <router-link :to="{ name: 'JobDetails', params: {id: job.id} }">
        <h3>{{job.title}}</h3>
     </router-link>
  </div>
</template>

<script>
export default {
    data() {
        return {
            jobs: [
                {title:'Ninja UX Designer', id: 1, details: 'lorem'},
                {title:'Ninja Web Developer', id: 2, details: 'lorem'},
                {title:'Ninja Vue Developer', id: 3, details: 'lorem'},
            ]
        }
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