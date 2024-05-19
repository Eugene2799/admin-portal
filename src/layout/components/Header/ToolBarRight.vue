<template>
  <div class="tool-bar-ri">
    <div class="header-icon">
      <SearchMenu id="searchMenu" />
      <el-tooltip content="主题切换" effect="dark" placement="bottom">
        <ThemeSetting id="themeSetting" />
      </el-tooltip>
      <el-tooltip content="全屏预览" effect="dark" placement="bottom">
        <Fullscreen id="fullscreen" />
      </el-tooltip>
    </div>
    <span class="username">{{ loginName }}</span>
    <Avatar />
  </div>
</template>

<script setup lang="ts">
import { useUserStore } from "@/store/modules/user";
import SearchMenu from "./components/SearchMenu.vue";
import ThemeSetting from "./components/ThemeSetting.vue";
import Fullscreen from "./components/Fullscreen.vue";
import Avatar from "./components/Avatar.vue";

const userStore = useUserStore();
const loginName = computed(() => userStore.loginName);
</script>

<style scoped lang="scss">
.tool-bar-ri {
  display: flex;
  align-items: center;
  justify-content: center;
  padding-right: 25px;

  .header-icon {
    display: flex;
    align-items: center;

    * {
      margin-left: 21px;
    }
  }

  .username {
    margin: 0 20px;
    font-size: 15px;
  }
}
</style>
