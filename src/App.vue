<template>
  <div class="container">
    <div class="mail-box">
      <app-sidebar :messages="messages"></app-sidebar>
      <app-content></app-content>
    </div>
  </div>
</template>

<script>
import Sidebar from './components/Sidebar'
import Content from './components/Content'
import messages from './data/messages'

export default {
  data() {
    return {
      messages: messages
    };
  },
  components: {
    appSidebar: Sidebar,
    appContent: Content,  
  }
}
</script>

<style>
</style>
