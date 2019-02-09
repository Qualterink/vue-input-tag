<template>
  <div id="app">
    <h1>Vue input tag</h1>
    <InputTag
      class="input-tag-component"
      :min-length="minLength"
      :max-length="maxLength"
      :max-quantity-tags="maxQuantityTags"
      :show-notyfication="showNotyfication"
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
      minLength: 1,
      maxLength: 50,
      showNotyfication: true,
      maxQuantityTags: 15
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
  font-family: 'Montserrat', sans-serif;
}
h1 {
  margin-top:3rem;
}
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.input-tag-component {
  margin-top:3rem;
  width:80%;
  margin-left:10%;
}
</style>
