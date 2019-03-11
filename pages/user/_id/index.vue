<template>
  <div>
    <div>{{ user.id }}</div>
    <div>{{ user.name }}</div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  asyncData (context) {
    console.log(context.route.params);
    return axios.get(`https://jsonplaceholder.typicode.com/users/${context.route.params.id}`)
      .then(res => {
        console.log(res);
        return {
          user: res.data
        }
      })
  },
  created () {
    return axios.get(`https://jsonplaceholder.typicode.com/users/`)
      .then(res => {
        console.log(res);
      })
  },
  mounted () {
    
  }
}
</script>

<style scoped>

</style>