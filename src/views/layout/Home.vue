<template>
  <div class="home">
    <div class="menuList">
      <a-menu
        :default-selected-keys="['1']"
        :default-open-keys="['sub1']"
        mode="inline"
        theme="dark"
        :inline-collapsed="collapsed"
      >
        <a-menu-item key="1">
          <a-icon type="home" />
          <span>首页</span>
        </a-menu-item>
        <a-sub-menu key="sub1">
          <span slot="title"
            ><a-icon type="layout" /><span>商品管理</span></span
          >
          <a-menu-item key="5">商品列表</a-menu-item>
          <a-menu-item key="6">添加商品</a-menu-item>
        </a-sub-menu>
      </a-menu>
    </div>
    <div style="border-bottom: 1px solid #ddd; padding-top: 15px">
      <div :class="[collapsed ? 'btnlot' : 'btn']">
        <a-button
          type="primary"
          style="margin-bottom: 16px"
          @click="toggleCollapsed"
        >
          <a-icon :type="collapsed ? 'menu-unfold' : 'menu-fold'" />
        </a-button>
      </div>
      <div class="breadcrumb">
        <a-breadcrumb>
          <a-breadcrumb-item>首页</a-breadcrumb-item>
          <a-breadcrumb-item><a href="">统计</a></a-breadcrumb-item>
        </a-breadcrumb>
      </div>
      <div class="userMsg">
        <a-dropdown :trigger="['click']">
          <a class="ant-dropdown-link" @click="(e) => e.preventDefault()">
            欢迎ying<a-icon type="down" />
          </a>
          <a-menu slot="overlay">
            <a-menu-item key="0">登出</a-menu-item>
          </a-menu>
        </a-dropdown>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      collapsed: false,
    };
  },
  methods: {
    toggleCollapsed() {
      this.collapsed = !this.collapsed;
    },
  },
};
</script>
<style lang="less" scoped>
.home {
  .menuList {
    width: 180px;
    position: fixed;
    height: 100%;
    .ant-menu {
      height: 100%;
    }
  }
  .btn {
    display: inline-block;
    margin-left: 190px;
    transition: all 0.2s;
  }
  .btnlot {
    display: inline-block;
    margin-left: 90px;
    transition: all 0.2s;
  }
  .breadcrumb {
    display: inline-block;
    margin-left: 20px;
  }
  .userMsg {
    margin-right: 30px;
    margin-top: 5px;
    float: right;
  }
}
</style>
