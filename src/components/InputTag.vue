<template>
  <div class="wrapper">
    <ul class="wrapper-list">
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
          title="Add tag"
          :placeholder="placeholder"
          v-model="inputValue"
          @keyup.enter="addTag"
          @blur="addTag">
        <span class="visuallyhidden">Add new tag</span>
      </li>
    </ul>
    <span 
      v-if="showNotyfication" 
      class="notyfication" 
      :class="[isDuplicated ? 'notyfication--active' : '']">
        Tag already exists
      </span>
  </div>
</template>

<script>
export default {
  name: 'InputTag',
  props: {
    placeholder: { required: false, default: 'Add tag', type: String },
    minLength: { required: false, default: 1, type: Number },
    showNotyfication: { required:false, default: true, type: Boolean }
  },
  data () {
    return {
      tagList: ['lorem', 'lorem ipsum', 'lorem ipsum dolor?'],
      inputValue: '',
      isDuplicated: false
    }
  },
  methods: {
    deleteTag (key) {
      this.tagList = this.tagList.filter((item, listKey) => listKey !== key)
    },
    addTag () {
      if (this.inputValue.trim().length >= this.minLength) {
        if (!this.tagList.find(item => item === this.inputValue.trim())) {
          this.isDuplicated = false
          this.tagList.push(this.inputValue.trim().toString())
          this.inputValue = ''
        } else {
          this.isDuplicated = true
        }
      }
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
  position: relative;
  margin-top:100px;
  width:80%;
  margin-left:10%;
}
.wrapper-list {
  font-size: 1rem;
  display: flex;
  flex-wrap: wrap;
  border: 1px solid #64ccff;
  list-style-type: none;
  margin:0;
  padding:0;
  font-size:1.2rem;
  box-sizing: border-box;
  border-radius: .125rem;
}
.item {
  padding:.25rem;
}
.wrapper-tags {
  border: 1px solid #64ccff;
  padding:.25rem .5rem;
  background-color: #3bf;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-radius: .125rem;
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
  border-bottom:1px solid #3bf;
  padding:.25rem .5rem;
  font-size:1.2rem;
  font-weight: 300;
}
.input-tag:focus {
  border:1px solid #3bf;
}
.notyfication {
  position: absolute;
  top:0;
  left: 50%;
  transform: translate(-50%, 0);
  font-size: 1.5rem;
  color: #333;
  background-color: #b7e7ff;
  padding: .25rem;
  width: 100%;
  border: 1px solid #64ccff;
  border-bottom: transparent;
  transition: transform .2s ease-in, 
              opacity .2s ease-in-out,
              visibility .3s;
  opacity:0;
  visibility: hidden;
}
.notyfication.notyfication--active {
  transform: translate(-50%, -2.125rem);
  opacity:1;
  visibility: visible;
}
</style>
