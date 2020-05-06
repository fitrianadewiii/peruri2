<template >
  <section class="mb-5" style=""   >
     <Chat
      
        iconColorProp="#275EFE"
        messageOutColorProp="#4d9e93"
        messageInColorProp="#f1f0f0"
        messageBackgroundColorProp="#ffffff"
        :messageListProp="messageList"
        :initOpenProp="initOpen"
        @onToggleOpen="handleToggleOpen"
        @onMessageWasSent="handleMessageReceived"
        
      />
    <Navbar />
    <nuxt class="p-3"   />
  </section>
</template>
<script>
import {Chat} from 'vue-chat-widget'
// import incomingMessageSound from '../assets/notification.mp3' // pick an audio file for chat response 
import Vue from 'vue'
import { BootstrapVue, BootstrapVueIcons } from 'bootstrap-vue'
Vue.use(BootstrapVue)
Vue.use(BootstrapVueIcons)
import VueDocPreview from 'vue-doc-preview'
import VueSweetalert2 from 'vue-sweetalert2';
Vue.use(VueSweetalert2);
import Navbar from '@@/components/Navbar'
export default {
  components: {
        Navbar,
        Chat,      
    },
    data: () => {
    return {
      messageList: [],
      initOpen: false,
      toggledOpen: false
    }
  },
  methods: {
    // Send message from you
    handleMessageReceived(message) {
      this.messageList.push(message)
    },
    // Receive message from them (handled by you with your backend)
    handleMessageResponse(message) {
       if (message.length > 0) {
            this.messageList.push({ body: message, author: 'them' })
        }
    },
    // Chat toggled open event emitted
    handleToggleOpen(open) {
      this.toggledOpen = open
      // connect/disconnect websocket or something
    },
    // Audible chat response noise, use whatever noise you want
    handleMessageResponseSound() {
      const audio = new Audio(incomingMessageSound)
      audio.addEventListener('loadeddata', () => {
        audio.play()
      })
    },
  },
  // init chat with a message
  mounted() {
    this.messageList.push({ body: 'Welcome to the chat, I\'m David!', author: 'them' })
  },
  watch: {
    messageList: function(newList) {
      const nextMessage = newList[newList.length - 1]
      const isIncoming = (nextMessage || {}).author !== 'you'
      if (isIncoming && this.toggledOpen) {
        this.handleMessageResponseSound()
      }
    }
  }
  
}
</script>

<style>
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}
.close-chat svg[data-v-6d002ea3] {
    position: relative;
    left: 9px;
    top: 4px;
    width: 15px;
}
.chat-container[data-v-6d002ea3] {
    position: fixed;
    bottom: 50px;
    right: 50px;
    max-width: 300px;
    width: 80%;
    z-index: 10000;
    -webkit-transform: scale(0);
    transform: scale(0);
    -webkit-transform-origin: right bottom;
    transform-origin: right bottom;
}
.open-chat[data-v-6d002ea3] {
    position: fixed;
    width: 40px;
    right: 50px;
    bottom: 25px;
    cursor: pointer;
    z-index: 900;
    -webkit-transform: scale(0);
    transform: scale(0);
}
</style>