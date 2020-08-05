<template>
    <el-container>
      <el-aside style="width: 200px;margin-top: 20px">
        <switch></switch>
        <side-menu></side-menu>
      </el-aside>
      <el-main>
        <book class="book-area"></book>
      </el-main>
    </el-container>
</template>

<script>
import SideMenu from './SideMenu'
import Book from './Book'
export default {
  name: 'LibraryIndex',
  components: {Book, SideMenu}
}
</script>

<style scoped>
  .book-area {
    width: 1200px;
    margin-left: auto;
    margin-right: auto;
  }
</style>
