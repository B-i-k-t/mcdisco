<template>
  <p class="folder">{{name}}</p>
  <ul>
    <template v-for="folder in folders">
      <li class="folder_item"> 
        <FolderView :name="folder.name" :folders="folder.folders" :files="folder.files"/>
      </li>
    </template>
  </ul>
  <ul class="file_list">
    <template v-for="file in files">
      <li class="file_item">
        <FileView :name="file.name"/>
      </li>
    </template>
  </ul>
</template>

<script>
import FileView from "./FileView";
export default {
  name: 'FolderView',
  components: {FileView},
  props: {
    name: String,
    folders:Array,
    files:Array
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
p{
  padding: 0;
  margin: 0;
  line-height: 32px;
}
.folder{
  color: orangered;
}
.folder_item{
  list-style: none;
  background: url(../img/folder_icon.png) no-repeat 0 1px;
  padding-left: 34px;
}
.file_item{
  list-style: none;
  background: url(../img/file_icon.png) no-repeat 0 1px;
  padding-left: 34px;
}
</style>
