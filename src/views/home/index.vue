<template>
  <t-layout-page class="dashboard-container">
    <t-layout-page-item>
      <!-- 用户信息 -->
      <div class="mb-8">
        <div class="flex-box flex-between flex-wrap">
          <div class="flex-box flex-ver-v">
            <el-icon class="user-avatar"><Avatar /></el-icon>
            <div>
              当前登陆账号是：{{
                loginName === "user"
                  ? `${loginName}（即：游客账号---> 没有大屏、高德地图菜单；系统管理--没有部分按钮）`
                  : `${loginName}（即：超管账号）`
              }}
            </div>
          </div>
        </div>
      </div>
    </t-layout-page-item>
    <t-layout-page-item>
      <!-- Echarts 图表 -->
      <el-row :gutter="40">
        <el-col :sm="24" :lg="8" class="mb-4">
          <BarChart id="barChart" height="400px" width="100%" class="bg-[var(--el-bg-color-overlay)]" />
        </el-col>

        <el-col :xs="24" :sm="12" :lg="8" class="mb-4">
          <PieChart id="pieChart" height="400px" width="100%" class="bg-[var(--el-bg-color-overlay)]" />
        </el-col>

        <el-col :xs="24" :sm="12" :lg="8" class="mb-4">
          <RadarChart id="radarChart" height="400px" width="100%" class="bg-[var(--el-bg-color-overlay)]" />
        </el-col>
      </el-row>
    </t-layout-page-item>
  </t-layout-page>
</template>
<script setup lang="ts" name="Dashboard">
import { useUserStore } from "@/store/modules/user";
import BarChart from "./components/BarChart.vue";
import PieChart from "./components/PieChart.vue";
import RadarChart from "./components/RadarChart.vue";

const userStore = useUserStore();
const loginName = computed(() => userStore.loginName);
const { appContext } = getCurrentInstance() as any;
const global = appContext.config.globalProperties;
// 获取所有业务api接口
console.log("获取所有业务api接口", global.$api);
</script>

<style lang="scss" scoped>
.dashboard-container {
  position: relative;

  .user-avatar {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    font-size: 2em;
    color: var(--el-color-primary);
  }
}
</style>
