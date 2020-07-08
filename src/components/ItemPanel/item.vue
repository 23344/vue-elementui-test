<template>
  <div class="item">
        this is itempanel's item page.
  </div>
</template>

<script>
import eventBus from "@/utils/eventBus";
export default {
  data() {
    return {
      page: null,
      command:null
    };
  },
  created() {
    this.bindEvent();
  },
  methods: {
    bindEvent() {
      eventBus.$on("afterAddPage", page => {
        this.page = page;
      });
    },
  }
};
</script>

<style scoped>
.item {
  height: 100%;
  position: absolute;
  left: 0px;
  z-index: 2;
  background: #f7f9fb;
  width: 200px;
  padding-top: 8px;
  border-right: 1px solid #e6e9ed;
}
</style>