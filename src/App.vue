<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Hello Mernante!"/>
  <button @click="runScript()">RUN SCRIPT</button>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import axios from 'axios'
export default {
  name: 'App',
  components: {
    HelloWorld
  },
  setup() {
    return {

    }
  },
  methods: {
    async runScript() {
      axios.defaults.headers.common['Access-Control-Allow-Origin'] = '*';
      const res = await axios.post("https://snowballcompany.webhook.office.com/webhookb2/710b9309-8b4d-4ba8-9574-921f48cdfc44@caf560d4-f4f6-4071-8442-abab6b7b7122/IncomingWebhook/56db4c9f8694475f93b83e9f608dcebd/6d105f93-f0c4-4e82-adea-d784761d81bf", 
      {
        "@type": "MessageCard",
        "@context": "http://schema.org/extensions",
        "themeColor": "0076D7",
        "summary": "Hooks",
        "sections": [{
            "activityTitle": "Test Only",
            "activitySubtitle": "On Project Tango",
            "markdown": true
        }]
      },{
        headers: {
          "Content-Type": "application/json"
        }
      }
      );

      console.log(res)
    }
  },
  created() {
    console.log('Created...')
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
