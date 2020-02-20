<template>
  <div>
    <h4>{{ msg }}</h4>
    <!--p>{{ newText }}</p-->
    <button @click="sendText">Send Text</button>
  </div>
</template>

<script>
export default {
  name: "firstChild",
  props: ["newText"],
  data() {
    return {
      // eslint-disable-next-line vue/no-dupe-keys
      msg: "hello from first child component",
      text: "I am coming from First Child Component"
    };
  },
  methods: {
    sendText() {
      this.newText = this.text;
      // eslint-disable-next-line no-unreachable
      this.$emit("sendText", this.newText);
    }
  }
};
</script>
