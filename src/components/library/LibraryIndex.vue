<template>
    <el-container>
      <el-aside style="width: 200px;margin-top: 20px">
        <switch></switch>
        <side-menu @indexSelect="listByCategory" ref="sideMenu"></side-menu>
      </el-aside>
      <el-main>
        <book class="book-area" ref="booksArea"></book>
      </el-main>
    </el-container>
</template>

<script>
import SideMenu from './SideMenu'
import Book from './Book'
export default {
  name: 'AppLibrary',
  components: {Book, SideMenu},
  methods:{
    listByCategory () {
      var _this = this
      var cid = this.$refs.sideMenu.cid
      var url = 'category/' + cid + '/books'
      _this.$axios.get(url).then(resp => {
        if (resp && resp.status === 200) {
          _this.$refs.booksArea.books = resp.data
        }
      })
    }
  }
}
</script>

<style scoped>
  .book-area {
    width: 1200px;
    margin-left: auto;
    margin-right: auto;
  }
</style>
