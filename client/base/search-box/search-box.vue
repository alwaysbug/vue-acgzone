<template>
    <div class="search-box">
        <input type="text" placeholder="搜索一下下菊花又不会坏……" v-model="key">
        <div @click="onSearch" class="searcher">
            <i class="icon-font icon-search"></i>
        </div>

    </div>
</template>

<script>
  export default {
    data() {
      return {
        key: ''
      }
    },
    methods:{
      onSearch(){
        this.$router.push({
          path: `/search/${this.key}`
        })
      }
    }
  }
</script>

<style scoped lang="stylus">
    @import "~common/stylus/variable"
    .search-box
        position absolute
        left: 50%
        transform translate(-50%, 0)
        top: 12px
        .searcher
            display inline-block
        input
            color: $color
            padding: 12px 30px 12px 15px
            border-radius 20px
            background $bg-color
            width 250px
            box-shadow 0 1px 2px rgba(29, 36, 52, .8)
            box-sizing: border-box
        input:focus
            border: 1px solid $blue-color
            padding: 10px 28px 10px 13px
        .icon-search
            background $blue-color
            border-radius 50%
            color: #fff
            padding: 5px
            position: relative
            right: 38px
            top: 1px
</style>