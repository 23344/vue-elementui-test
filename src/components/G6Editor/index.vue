<template>
  <div id="mountNode" :style="{width:width,height:height}">
    <div class="editor" >
      <!-- <context-menu />
      <div class="bottom-container">
        <detail-panel />
      </div> -->
      <!-- hahahaahahah -->
        <el-container>
            <el-aside width="200px">
                <!-- ItemPanel -->
                <item-panel />
                <!-- <minimap /> -->
            </el-aside>
            <el-main>
                <!-- <page :height="height" :width="width"  :data="data" /> -->
                hahahamain
            </el-main>
            <Flow />
        </el-container>
    </div>
    
  </div>

    
</template>

<script>
import ItemPanel from "../ItemPanel";
// import DetailPanel from "../DetailPanel";
// import Minimap from "../Minimap";
// import Page from "../Page";
// import Flow from "../Flow"
// import ContextMenu from "../ContextMenu";
// import Editor from "@/components/Base/Editor";
// import command from "@/command";
export default {
  name: "G6Editor",
  components: {
    // Toolbar,
    ItemPanel
    // DetailPanel,
    // Minimap,
    // Page,
    // ContextMenu,
    // Flow
  },
  props: {
    height: {
      type: Number,
      default: document.documentElement.clientHeight
    },
    width: {
      type: Number,
      default: document.documentElement.clientWidth
    },
    data: {
      type: Object,
      default: () => {}
    }
  },
  created() {
    this.init();
  },
  data() {
    return {
      editor: {},
      command: null
    };
  },
  methods: {
    init() {
      this.editor = new Editor();
      this.command = new command(this.editor);
    }
  }
};
</script>

<style scoped>
.editor {
  position: relative;
  width: 100%;
  height: 400px;
  background-color: #ff00ff;
  user-select: none;
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
}
/* .bottom-container {
  position: relative;
} */
</style>