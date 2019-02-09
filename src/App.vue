<template>
  <div id="app">
    <h1>Vue input tag</h1>
    <h2>Options</h2>
    <ul class="option">
      <li class="option-item">Placeholder: {{ placeholder }}</li>
      <li class="option-item">Min length tag: {{ minLength }}</li>
      <li class="option-item">Max length tag: {{ maxLength }}</li>
      <li class="option-item">Show notyfication: {{ showNotyfication }}</li>
      <li class="option-item">Quantity tags: {{ maxQuantityTags }}</li>
    </ul>
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
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding:3rem;
}
h2 {
  margin-top:2rem;
  text-align: left;
}
.option {
  text-align: left;
  list-style-type: none;
}
.option-item {
  margin:.625rem;
}
.input-tag-component {
  margin-top:3rem;
}
</style>
