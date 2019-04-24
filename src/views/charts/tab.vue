<template>
  <div class="tab-container">
    <el-tabs v-model="activeName" type="card" @tab-click="handleClick">
      <el-tab-pane class="tab-pane" label="用户管理" name="first">
        <mix-chart v-if="activeName === 'first'" id="tab_mix_chart" ref="tab_mix_chart" height="100%" width="100%" />
      </el-tab-pane>
      <el-tab-pane class="tab-pane" label="配置管理" name="second">
        <line-marker v-if="activeName === 'second'" id="tab_line_marker" ref="tab_line_marker" height="100%" width="100%" />
      </el-tab-pane>
      <el-tab-pane class="tab-pane" label="角色管理" name="third">
        <keyboard v-if="activeName === 'third'" id="tab_keyboard" ref="tab_keyboard" height="100%" width="100%" />
      </el-tab-pane>
    </el-tabs>
  </div>
</template>

<script>
import MixChart from '@/components/Charts/MixChart'
import LineMarker from '@/components/Charts/LineMarker'
import Keyboard from '@/components/Charts/Keyboard'
export default {
  name: 'TabChart',
  components: {
    MixChart,
    LineMarker,
    Keyboard
  },
  data() {
    return {
      activeName: 'first'
    }
  },
  methods: {
    handleClick(tab, e) {

    }
  }
}
</script>

<style lang='scss' scoped>
.tab-container {
  width: 100%;
  height: calc(100vh - 84px);
  padding: 20px;
  .tab-pane {
    width: 100%;
    height: calc(100vh - 170px);
  }
}
</style>
