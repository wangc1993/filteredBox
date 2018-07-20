<template>
  <div class="filteredBox">
    <span v-for="(tag, index) in tagArr" :key="index" class="filterTag" :class="tag.name.length > 9 ? 'filterTag-2' : ''">
      {{tag.name}}
      <i @click="deleteTag(index)" class="el-icon-close filterTag-icon"></i>
    </span>
  </div>
</template>

<script>
  export default {
    name: 'filteredBox',
    props: ['tagArr'],
    data() {
      return {
        tagVisible: true
      }
    },
    methods: {
      deleteTag(index) {
        this.tagArr.splice(index, 1);
        this.$emit('deleteTag', this.tagArr);
      }
    }
  }
</script>

<style lang="scss">
  .filteredBox {
    width: 100%;
    min-width: 1366px;
    background-color: #f8f9f9;
    display: -webkit-box;
    margin-top: 10px;
    .filterTag-2 {
      width: calc((100% - 128px)/4 + 16px) !important;
    }
    .filterTag {
      display: inline-block;
      position: relative;
      width: calc((100% - 128px)/8);
      background-color: #ddd;
      padding: 0 10px;
      height: 32px;
      line-height: 30px;
      text-align: center;
      font-size: 12px;
      color: #333;
      border-radius: 4px;
      box-sizing: border-box;
      border: 1px solid #ddd;
      white-space: nowrap;
      margin: 5px 8px;
      .filterTag-icon {
        border-radius: 50%;
        text-align: center;
        position: absolute;
        cursor: pointer;
        font-size: 12px;
        height: 16px;
        width: 16px;
        line-height: 16px;
        right: 5px;
        top: 7px;
        color: #999;
        &:hover {
          background-color: #409EFF;
          color: #fff;
        }
      }
    }
  }
</style>
