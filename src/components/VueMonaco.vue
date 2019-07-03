<template>
  <div>
    <MonacoEditor
      :diffEditor="true"
      :original="left"
      :value="right"
      class="editor"
      language="javascript"
      ref="diffViewEditor"
    />
  </div>
</template>

<script>
import MonacoEditor from 'vue-monaco'
// const monaco = require('monaco-editor')
// const monaco = require('monaco-editor/esm/vs/editor/editor.api')

export default {
  components: {
    MonacoEditor
  },

  data() {
    return {
      left: `import Vue from 'vue'
import App from './App.vue'

Vue.config.productionTip = false

new Vue({
  render: h => h(App),
}).$mount('#app')
`,
      right: `module.exports = {
  root: true,
  env: {
    node: true
  },
  'extends': [
    'plugin:vue/essential',
    'eslint:recommended'
  ],
  rules: {
    'no-console': process.env.NODE_ENV === 'production' ? 'error' : 'off',
    'no-debugger': process.env.NODE_ENV === 'production' ? 'error' : 'off'
  },
  parserOptions: {
    parser: 'babel-eslint'
  }
}
`
    }
  },
  methods: {
    setLang(lang) {
      monaco.editor.setModelLanguage(
        this.$refs.diffViewEditor.getModifiedEditor().getModel(),
        lang
      )
      monaco.editor.setModelLanguage(
        this.$refs.diffViewEditor.getEditor().getModel(),
        lang
      )
    },
    setTheme(theme) {
      monaco.editor.setTheme(theme)
    }
  }
}
</script>

<style>
.editor {
  width: 600px;
  height: 800px;
}
</style>
