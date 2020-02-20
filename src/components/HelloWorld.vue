<template>
  <div id="hello">
    <h1>{{ newTitle }}</h1>
    <button @click="changeTitle">Change Title</button>
    <h4>{{ msg }}</h4>
    <p>{{ newText }}</p>
  </div>
</template>

<script>
export default {
  props: ["newTitle", "newText"],
  name: "hello",
  data() {
    return {
      // eslint-disable-next-line vue/no-dupe-keys
      msg: "Welcome From Hello World"
    };
  },
  methods: {
    changeTitle() {
      this.newTitle = "Title was Change by Hello World Child";
      this.$emit("changeTitle", this.newTitle);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
