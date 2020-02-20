<template>
  <div id="app">
    <h1>{{ title }}</h1>
    <input type="text" v-model="title" />
    <!--p>{{ text }}</p-->
    <hr />
    <div>
      <app-HelloWorld
        v-on:changeTitle="title = $event"
        v-bind:newTitle="title"
        :newText="text"
      ></app-HelloWorld>
      <hr />
      <app-firstChild
        v-on:sendText="text = $event"
        v-bind:newText="text"
      ></app-firstChild>
    </div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import firstChild from "./components/firstchild.vue";

export default {
  data() {
    return {
      title: "Our Title From Parent",
      text: "I am coming from App Vue"
    };
  },
  name: "app",
  components: {
    "app-HelloWorld": HelloWorld,
    "app-firstChild": firstChild
  }
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
