<template>

  <a-layout style="min-height: 100vh">

    <!-- <header> -->

    <a-layout-header style="background: #5aa700; padding: 0">

    </a-layout-header>
    <!-- <header> -->

    <a-layout style="min-height: calc(100vh - 64px)">

      <a-layout>
        <!-- <a-layout-header style="background: #fff; padding: 0">
          <menu-unfold-outlined v-if="collapsed" class="trigger" @click="() => (collapsed = !collapsed)" />
          <menu-fold-outlined v-else class="trigger" @click="() => (collapsed = !collapsed)" />
        </a-layout-header> -->

        <left-menu :collapsed="collapsed"></left-menu>

        <!-- 主体 -->
        <a-layout-content :style="{ margin: '24px 16px', padding: '24px', background: '#fff', minHeight: '280px' }">

          <div v-for="(d,index) in counter" :key="index">
            <dom :mess="d.d" :info="d.t"></dom>
          </div>
          <a-empty :image="simpleImage" />
        </a-layout-content>
        <!-- 主体 -->
<!-- 
        <a-layout-footer style="text-align: center">
          Ant Design ©2018 Created by Ant UED
        </a-layout-footer> -->
      </a-layout>

      <a-layout-sider :style="{ overflow: 'auto', height: '100vh', position: 'fixed', right: 0 }">
        <!-- <div class="logo" /> -->
        <a-menu mode="inline" v-model:selectedKeys="selectedKeys">
          <a-menu-item key="1">
            <user-outlined />
            <span>nav 1</span>
          </a-menu-item>
          <a-menu-item key="2">
            <video-camera-outlined />
            <span>nav 2</span>
          </a-menu-item>
          <a-menu-item key="3">
            <upload-outlined />
            <span>nav 3</span>
          </a-menu-item>
        </a-menu>
      </a-layout-sider>
    </a-layout>
  </a-layout>
</template>
<script >
  import {
    UserOutlined,
    VideoCameraOutlined,
    UploadOutlined,
    MenuUnfoldOutlined,
    MenuFoldOutlined,    
  } from '@ant-design/icons-vue';

  import { defineComponent, ref } from 'vue';

  import LeftMenu from '@/components/common/LeftMenu';

  import { Empty } from 'ant-design-vue';

  export default defineComponent({
    dara(){
      return{
        counter: Array
      }
    },
    components: {
      UserOutlined,
      VideoCameraOutlined,
      UploadOutlined,
      MenuUnfoldOutlined,
      MenuFoldOutlined,
      LeftMenu
    },

    setup() {
      return {
        selectedKeys: ref(['1']),
        collapsed: ref(false),
        simpleImage: Empty.PRESENTED_IMAGE_SIMPLE,
      };
    },

  });
</script>
<style lang="less">
  .Rose-lists {
    padding: 8px 0;
    width: 100%;
    height: 100%;
  }

  .Rose-para {
    position: relative;
    overflow: hidden;
    padding: 0 10px 10px;
    margin: 0;

  }

  .Rose-menu-item {
    color: #2c3e50;
    font-size: 12px;
    display: block;
    width: 48%;
    line-height: 26px;
    position: relative;
    float: left;
    left: 0;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    margin: 1%;
    color: #333;
    border: 1px solid #f4f6fc;

    a {
      display: block;
      cursor: move;
      background: #f4f6fc;
      border: 1px solid #f4f6fc;
      padding: 0px 5px;
      color: #333;


      span {
        display: inline-block;
        vertical-align: middle;
      }
    }
  }

  #components-layout-demo-custom-trigger .trigger {
    font-size: 18px;
    line-height: 64px;
    padding: 0 24px;
    cursor: pointer;
    transition: color 0.3s;
  }

  #components-layout-demo-custom-trigger .trigger:hover {
    color: #1890ff;
  }

  #components-layout-demo-custom-trigger .logo {
    height: 32px;
    background: rgba(255, 255, 255, 0.3);
    margin: 16px;
  }

  .site-layout .site-layout-background {
    background: #fff;
  }
</style>