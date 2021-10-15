<template>
  <div>
    <MessageList :messages="messages" />
    <MessageForm :on-send="(message) => onSend(message)"/>
  </div>
</template>

<script>
import MessageList from "@/components/show/MessageList";
import MessageForm from "@/components/form/MessageForm";

export default {
  name: 'App',
  components: {
    MessageForm,
    MessageList
  },
  data () {
    return {
      connection: null,
      messages: []
    }
  },
  methods: {
    onSend: function (message) {
      console.log(message)
      this.connection.send(message)
    }
  },
  mounted() {
    this.connection = new WebSocket("")

    this.connection.onopen = function (event) {
      console.log(event)
      console.log("Success")
    }

    this.connection.onmessage = function (event) {
      this.messages.add(event)
    }
  }
}
</script>
