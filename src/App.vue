<template>
  <div>
    <Header></Header>
    <div class="container">
      <Add :addComment="addComment"></Add>
      <List :coms="comments" :deleteComment="deleteComment"></List>
    </div>
  </div>
</template>

<script>
import Add from "./components/Add";
import Header from "./components/Header";
import List from "./components/List";

export default {
  data() {
    return {
      comments: [
        {
          id: 1,
          content: "vue是啥？？",
          username: "王海峰",
        },
        {
          id: 2,
          content: "那还用说？？必须牛逼",
          username: "尤雨溪",
        },
        {
          id: 3,
          content: "还行",
          username: "万民庆",
        },
      ],
    };
  },
  components: {
    Header,
    Add,
    List,
  },

  methods: {
    /**
     * 数据在哪，操作数据的方法就在那
     */
    addComment(comment) {
      // console.log(comment);
      this.comments.unshift(comment);
    },

    deleteComment(index){
      this.comments.splice(index, 1)
    }
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
