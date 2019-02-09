<template>
  <div id="app">
    <InputTag
      
      :placeholder="placeholder"/>
  </div>
</template>

<script>
import InputTag from './components/InputTag'
export default {
  name: 'app',
  components: { InputTag },
  data () {
    return {
      placeholder: "Add tag",
      minLength: 1
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  padding:0;
  margin:0;
}
html {
  font-size: 16px;
}
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
