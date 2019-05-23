<template>
  <div id="app">
    <h1>在线翻译</h1>
    <h5>简单 / 易用 / 便捷</h5>
    <TranslateForm v-on:translateFormk="translateFormValuek"></TranslateForm>
    <translateOutput v-text="translateText" class="mt-20"></translateOutput>
  </div>
</template>

<script>
import TranslateForm from "./components/translateForm";
import TranslateOutput from "./components/translateOutput";
export default {
  name: "App",
  components: {
    TranslateForm,
    TranslateOutput
  },
  data() {
    return {
      translateText: ""
    };
  },
  methods: {
    translateFormValuek: function(text, language) {
      this.$http
        .get(
          "https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20190522T133438Z.9b0ec2a8e117101f.ff0ca2e3c50917c77d47a597a0b6030617503dd7&lang=" +
            language +
            "&text=" +
            text
        )
        .then(response => {
          this.translateText = response.body.text[0];
        });
    }
  }
};
</script>

<style scoped>
#app {
  max-width: 800px;
  margin: 0 auto;
  text-align: center;
}
.mt-20 {
  margin-top: 40px;
}
</style>
