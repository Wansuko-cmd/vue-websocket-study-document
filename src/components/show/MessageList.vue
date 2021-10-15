<template>
  <div>
    <div v-for="message in messages" :key="message">
      <MessageCard
          :text="message.text"
          :user-name="message.user_name"/>
    </div>
  </div>
</template>

<script>

import MessageCard from "@/components/show/MessageCard";

export default {
  components: { MessageCard },
  props: {
    messages: Array
  },
}
</script>
