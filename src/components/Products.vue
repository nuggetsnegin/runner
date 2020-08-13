<template>
  <h1>test</h1>
</template>

<script>
import axios from 'axios'
export default {
   /*using axios to make first api call for auth token and then another api call for the test data using the auth token*/ 
  mounted () {
    axios
      .post('https://api.getrunner.io/runner/v4/login', {
        "data": {
            "type": "login credentials",
            "attributes": {
                "email": "negin@getrunner.io",
                "password": "secret",
                "anonymousId": "34234234"
            }
        }
      })
      .then(response => (response.data.data.attributes.accessToken))
      .then(token => (
          axios.get('https://api.getrunner.io/runner/v4/code-test-product', { params: {}, headers: { "Authorization": `Bearer ${token}` } })))
  }

}
</script>

<style>

</style>