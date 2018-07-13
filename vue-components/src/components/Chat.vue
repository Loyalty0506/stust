<template>
  <div>
    <form @submit.prevent="submit">
      <input v-model="author"/>
      <input v-model="text"/>
      <button type="submit">Submit</button>
    </form>
    <div>
      <div v-for="chat in chats" :key="chat.id">
        {{chat.author}}: {{chat.text}}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      author: "",
      text: "",
      chats: []
    };
  },
  methods: {
    submit() {
      fetch("http://10.2.3.190:3001/chat", {
        headers: {
          "Content-Type": "application/json"
        },
        method: "POST",
        body: JSON.stringify({
          author: this.author,
          text: this.text
        })
      });
      this.text = "";
      this.text.focus();
    },
    getChat() {
      fetch("http://10.2.3.190:3001/chat")
        .then(rs => rs.json())
        .then(list => (this.chats = list));
    }
  },
  mounted() {
    this.timer = setInterval(this.getChat, 1000);
  },
  beforeDetroy() {
    clearInterval(this.timer);
  }
};
</script>