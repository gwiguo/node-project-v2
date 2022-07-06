<template>
  <el-row id="app" :style="{color:$store.state.color}">
    <el-col :span="4">
      <Nav></Nav>
    </el-col>
    <el-col :span="20" class="app_right_container">
      <router-view />
    </el-col>
  </el-row>
</template>

<script>
import Nav from "@/components/Nav";
import { mapState } from "vuex";

export default {
  components: {
    Nav,
  },
  computed:{
	...mapState(['setColor'])
  },
  mounted(){
	console.log(this.$store.state)
  },
  name: "App",
};
</script>

<style lang="less">
body,
html {
  height: 100%;
  margin: 0;
  padding: 0;
}
#app {
  height: 100%;
  overflow: hidden;
  margin-right: 0 !important;
  .app_right_container {
    overflow-y: auto;
  }
  .el-col {
    height: 100%;
  }
}
</style>
