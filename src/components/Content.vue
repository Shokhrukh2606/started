<template>
  <aside class="lg-side">
    <div class="inbox-head">
      <h3>{{currentView.title}}</h3>
    </div>
    <keep-alive>
      <component :is="currentView.tag"></component>
    </keep-alive>   
  </aside>
</template>

<script>
import Inbox from './Inbox'
import Sent from './Sent'
import Important from './Important'
import Trash from './Trash'
import ViewMessage from './ViewMessage'
import {eventBus} from '../main'
export default {
  name: "Content",
   created(){
    eventBus.$on('changeView', (data)=>{
      let temp=[{
        tag: data.tag,
        title: data.title
      }];
      this.history=temp.concat(this.history.splice(0))
    })
  },
  data() {
    return {
      history: [
        {
          tag: "app-inbox",
          title: "Inbox"
        }
      ]
    };
  },
  computed: {
    currentView() {
      return this.history[0];
    }
  },
    components: {
      appInbox: Inbox,
      appSent: Sent,
      appImportant: Important,
      appTrash: Trash,
      appViewMessage: ViewMessage
    }
};
</script>