<template>
  <div class="translateForm">
    <form v-on:submit="formSubmit">
      <div class="form-group mt-20">
        <input
          type="text"
          v-model="formSubmitValue"
          placeholder="请输入需要翻译的内容"
          class="form-control is-valid"
        >
      </div>
      <div class="form-group has-success">
        <select v-model="language" class="form-control form-control-sm">
          <option value>请选择语言</option>
          <option value="en">英语</option>
          <option value="ru">俄罗斯语</option>
          <option value="ko">korean</option>
          <option value="ja">janpenese</option>
        </select>
      </div>
      <input type="submit" value="提交" class="btn btn-warning">
    </form>
  </div>
</template>

<script>
export default {
  name: "translateForm",
  data() {
    return {
      formSubmitValue: "",
      language: ""
    };
  },
  methods: {
    formSubmit: function(e) {
      this.$emit("translateFormk", this.formSubmitValue, this.language);
      e.preventDefault();
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.mt-20 {
  margin-top: 40px;
}
</style>
