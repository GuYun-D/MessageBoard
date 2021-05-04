<template>
  <div class="col-md-4">
    <form class="form-horizontal">
      <div class="form-group">
        <label>用户名</label>
        <input
          type="text"
          class="form-control"
          v-model="username"
          placeholder="用户名"
        />
      </div>
      <div class="form-group">
        <label>评论内容</label>
        <textarea
          class="form-control"
          rows="6"
          placeholder="评论内容"
          v-model="content"
        ></textarea>
      </div>
      <div class="form-group">
        <div class="col-sm-offset-2 col-sm-10">
          <button type="button" class="btn btn-default pull-right" @click="add">
            提交
          </button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: "",
      content: "",
    };
  },

  methods: {
    add() {
      // 获取数据
      let { username, content } = this;

      // 去除空格
      if (username.trim() && content.trim()) {
        const id = Date.now();
        // 将数据变成对象
        const contentObj = {
          id,
          username,
          content,
        };

        // 将数据添加到comments数组中
        this.addComment(contentObj);
      } else {
        alert("请输入合法内容");
      }

      this.username = "";
      this.content = "";
    },
  },

  // props接收到的数据最终也会混入到vm中
  props: ["addComment"],
};
</script>

<style scoped>
</style>