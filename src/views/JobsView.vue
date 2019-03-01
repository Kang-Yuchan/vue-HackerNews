<template>
  <div>
    <div v-for="item in jobs">
      {{item.title}}
    </div>
  </div>
</template>

<script>
import {fetchJobsList} from '../api/api.js';

export default {
  data() {
    return {
      jobs: []
    }
  },
  created() {
    let vm = this;
    fetchJobsList()
      .then(response => {
        console.log(response);
        vm.jobs = response.data;
        })
      .catch(err => {
        console.log(err);
        });
  }
}
</script>
