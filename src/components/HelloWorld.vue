<template>
  <div ref="graph_container" class="graph_container" id="graphContainer"></div>
</template>

<script>
import { mxGraph } from 'mxgraph';
export default {
  name: 'HelloWorld',
  mounted() {
    // 创建画布
    var graph = new mxGraph(document.getElementById('graphContainer'));
    var parent = graph.getDefaultParent();
    // 开始更新画布
    graph.getModel().beginUpdate();
    try {
      // 插入节点
      let v1 = graph.insertVertex(parent, null, 'Hello,', 20, 20, 80, 30);
      let v2 = graph.insertVertex(parent, null, 'World!', 200, 150, 80, 30);
      // 插入连线
      graph.insertEdge(parent, null, '', v1, v2);
    } finally {
      // 画布更新结束
      graph.getModel().endUpdate();
    }
  },
};
</script>

<style></style>
