<template>
  <b-container>
    <b-card>
      <div class="chatbox">
        <b-row
          class="no-gutters"
          align-h="start"
          v-for="(message, inx) in chatHistory"
          :key="inx"
        >
          <b-col class="no-gutters" cols="8">
            <div>
              <p class="received-chat">{{ message }}</p>
            </div>
          </b-col>
        </b-row>
      </div>
      <chat-message-box :socket="socket"></chat-message-box>
    </b-card>
  </b-container>
</template>

<script>
import ChatMessageBox from "./ChatMessageBox.vue";
export default {
  props: ["socket"],
  components: {
    ChatMessageBox,
  },
  data() {
    return {
      chatHistory: [],
    };
  },
  mounted() {
    if (this.socket) {
      this.socket.on("/message", (message) => {
        if (message) {
          this.chatHistory.push(message.trim());
        }
      });
    }
  },
};
</script>