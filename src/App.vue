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
      // https://teams.microsoft.com/l/channel/19%3a92a4752be3b845af881f0912db68d97b%40thread.tacv2/Test-ServerLogs?groupId=710b9309-8b4d-4ba8-9574-921f48cdfc44&tenantId=caf560d4-f4f6-4071-8442-abab6b7b7122
    //   var card = {
    //     "type": "message",
    //     "attachments": [
    //         {
    //             "contentType": "application/vnd.microsoft.card.adaptive",
    //             "contentUrl": null,
    //             "content": {
    //                 "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    //                 "type": "AdaptiveCard",
    //                 "version": "1.2",
    //                 "body": [
    //                     {
    //                         "type": "TextBlock",
    //                         "text": "Submitted response:"
    //                     }
    //                 ]
    //             }
    //         }
    //     ]
    // }

      const res = await axios.post("http://localhost:3001/api/send?message=Test Only");

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
