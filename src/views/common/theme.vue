<template>
  <div>
    <el-form>
      <h2>布局设置</h2>
      <el-form-item label="导航条类型">
        <el-radio-group v-model="navbarLayoutType">
          <el-radio label="default" border>default</el-radio>
          <el-radio label="inverse" border>inverse</el-radio>
        </el-radio-group>
      </el-form-item>
      <el-form-item label="侧边栏皮肤">
        <el-radio-group v-model="sidebarLayoutSkin">
          <el-radio label="light" border>light</el-radio>
          <el-radio label="dark" border>dark</el-radio>
        </el-radio-group>
      </el-form-item>
      <el-form-item label="皮肤切换">
        <el-radio-group v-model="sidebarLayoutSkin">
          <el-switch v-model="theme" />
        </el-radio-group>
      </el-form-item>
    </el-form>
    <div class="block">
      <el-button type="primary">Primary</el-button>
      <el-button type="success">Success</el-button>
      <el-button type="info">Info</el-button>
      <el-button type="warning">Warning</el-button>
      <el-button type="danger">Danger</el-button>
    </div>
    <div class="block">
      <el-button type="primary" icon="el-icon-edit" />
      <el-button type="primary" icon="el-icon-share" />
      <el-button type="primary" icon="el-icon-delete" />
      <el-button type="primary" icon="el-icon-search">Search</el-button>
      <el-button type="primary">
        Upload
        <i class="el-icon-upload el-icon-right" />
      </el-button>
    </div>
    <div class="block">
      <el-tag v-for="tag in tags" :key="tag.type" :type="tag.type" class="tag-item">{{ tag.name }}</el-tag>
    </div>
    <div class="block">
      <el-radio-group v-model="radio">
        <el-radio :label="3">Option A</el-radio>
        <el-radio :label="6">Option B</el-radio>
        <el-radio :label="9">Option C</el-radio>
      </el-radio-group>
    </div>
  </div>
</template>

<script>
/* eslint-disable */
import { toggleClass } from "@/utils";
import "@/assets/custom-theme/index.css"; // the theme changed version element-ui css
export default {
  data() {
    return {
      theme: false,
      tags: [
        { name: 'Tag One', type: '' },
        { name: 'Tag Two', type: 'info' },
        { name: 'Tag Three', type: 'success' },
        { name: 'Tag Four', type: 'warning' },
        { name: 'Tag Five', type: 'danger' }
      ],
      radio: 3
    };
  },
  computed: {
    navbarLayoutType: {
      get() {
        return this.$store.state.common.navbarLayoutType;
      },
      set(val) {
        this.$store.commit("common/updateNavbarLayoutType", val);
      }
    },
    sidebarLayoutSkin: {
      get() {
        return this.$store.state.common.sidebarLayoutSkin;
      },
      set(val) {
        this.$store.commit("common/updateSidebarLayoutSkin", val);
      }
    }
  },
  watch: {
    theme() {
      toggleClass(document.body, "custom-theme");
    }
  }
};
</script>

<style lang="scss" scoped>
.block {
  padding: 30px 24px;
}
</style>
