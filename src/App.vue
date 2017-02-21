<template>
  <div id="app">
    <img src="./assets/logo.png">
    <MonacoEditor height="600" language="typescript" :code="code" :editorOptions="options" @mounted="onMounted" @codeChange="onCodeChange">
    </MonacoEditor>
  </div>
</template>

<script>
  import MonacoEditor from 'vue-monaco-editor'

  export default {
    name: 'app',
    components: {
      MonacoEditor
    },
    data () {
      return {
        code: '// Type away! \n',
        options: {
          selectOnLineNumbers: false
        }
      }
    },
    methods: {
      onMounted (editor) {
        this.editor = editor
      },
      onCodeChange (editor) {
        console.log(editor.getValue())
      }
    }
  }

</script>

<style>
</style>
