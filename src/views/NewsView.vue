<template>
  <div>
    <div v-for="user in users">
    {{user.title}}
    </div>
  </div>
</template>

<script>
import { fetchNewsList } from '../api/api.js';

export default {
  data() {
    return {
      users: []
    }
  },
  created() {
    let vm = this;
    fetchNewsList()
      .then(response => {
        console.log(response);
        vm.users = response.data;
        })
      .catch(err => {
        console.log(err);
        });
  }
}
</script>
