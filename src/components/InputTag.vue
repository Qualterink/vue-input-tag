<template>
  <ul class="wrapper">
    <li class="item" v-for="(item, key) in tagList" :key="key">
      <span class="wrapper-tags">
        <span class="tags" >{{ item }}</span>
        <button type="button" class="cross" title="Delete tag" @click="deleteTag(key)">
          <span class="visuallyhidden">Delete tag</span>
        </button>
      </span>
    </li>
    <li class="item">
      <input 
      class="input-tag"
      type="text"
      placeholder="Add tag">
    </li>
  </ul>
</template>

<script>
export default {
  name: 'InputTag',
  data () {
    return {
      tagList: ['lorem', 'lorem ipsum', 'lorem ipsum dolor?', 'lorem']
    }
  },
  methods: {
    deleteTag (key) {
      // eslint-disable-next-line
      console.log(key)
    }
  }
}
</script>

<style scoped>
.visuallyhidden {
    border: 0;
    clip: rect(0 0 0 0);
    height: 1px;
    margin: -1px;
    overflow: hidden;
    padding: 0;
    position: absolute;
    width: 1px;
    white-space: nowrap; /* 1 */
}
.visuallyhidden.focusable:active,
.visuallyhidden.focusable:focus {
    clip: auto;
    height: auto;
    margin: 0;
    overflow: visible;
    position: static;
    width: auto;
    white-space: inherit;
}
.wrapper {
  font-size: 1rem;
  display: flex;
  flex-wrap: wrap;
  border: 1px solid #2f4550;
  list-style-type: none;
  margin:0;
  padding:0;
  font-size:1.2rem;
  box-sizing: border-box;

  margin-top:100px;
  margin-left:10%;
  width:80%;
}
.item {
  padding:.25rem;
}
.wrapper-tags {
  border: 1px solid #3786ad;
  padding:.25rem .5rem;
  background-color: #45c1ff;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.tags {
  color:#fff;
}
.cross {
  margin-left:.225rem;
  height:1.5rem;
  width:1.5rem;
  cursor: pointer;
  position: relative;
  border:none;
  background-color:transparent;
  opacity:.7;
}
.cross:hover {
  opacity:1;
}
.cross::before, .cross::after {
  content: '';
  position: absolute;
  top:.3rem;
  right:.5rem;
  height: 1rem;
  width: .125rem;
  background-color: #333;
}
.cross:before {
  transform: rotate(45deg);
}
.cross:after {
  transform: rotate(-45deg);
}
.input-tag {
  border:1px solid transparent;
  padding:.25rem .5rem;
  font-size:1.2rem;
  font-weight: 300;
}
</style>
