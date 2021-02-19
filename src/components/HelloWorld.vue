<template>

  <a-layout style="min-height: 100vh">

    <!-- <header> -->

    <a-layout-header style="background: #5aa700; padding: 0">

    </a-layout-header>
    <!-- <header> -->

    <a-layout style="min-height: calc(100vh - 64px)">

      <a-layout>

        <left-menu 
        :menuitems="states.json"
        :collapsed="collapsed" @pushItem="addCounter"></left-menu>

        <!-- 主体 -->
        <a-layout-content :style="{ margin: '24px 16px', padding: '24px', background: '#fff', minHeight: '280px' }">

          <Content v-for="item in states.selected" 
          :key="item.id" 
          :text="item.text" 
          :icon="item.icon"
          :type="item.type">
          </Content>

          <a-empty :image="simpleImage" />
        </a-layout-content>
        <!-- 主体 -->

      </a-layout>

      <a-layout-sider :style="{ overflow: 'auto', height: '100vh', position: 'fixed', right: 0 }">
        <!-- <div class="logo" /> -->
        <!-- <a-menu mode="inline" v-model:selectedKeys="selectedKeys">
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
        </a-menu> -->
      </a-layout-sider>
    </a-layout>
  </a-layout>
</template>
<script lang="ts">
  import {
    // UserOutlined,
    // VideoCameraOutlined,
    // UploadOutlined  
  } from '@ant-design/icons-vue';

  import {
    defineComponent,
    ref,
    reactive
  } from 'vue';
import { SelectedFormItem } from '@/lib/interface';

  import LeftMenu from '@/components/common/LeftMenu';
  import Content from '@/components/common/Content';

  import {
    Empty
  } from 'ant-design-vue';



  export default defineComponent({
    dara() {
      return {
        counter: {
          type: Array
        }
      }
    },
    components: {
      // UserOutlined,
      // VideoCameraOutlined,
      // UploadOutlined,   
      LeftMenu,
      Content
    },

    setup() {
      const states = reactive({
        json: [{
            id: 1,
            icon: 'UserOutlined',
            type: 'input',
            text: '输入框'
          },
          {
            id: 2,
            icon: 'UserOutlined',
            type: 'textarea',
            text: '文本框'
          },
          {
            id: 3,
            icon: 'icon-number',
            type: 'select',
            text: '数字输入框'
          },
          {
            id: 4,
            icon: 'icon-drop_down_line',
            type: 'textarea',
            text: '下拉选择器'
          },
          {
            id: 5,
            icon: 'icon-duoxuanti',
            type: 'textarea',
            text: '多选框'
          },
          {
            id: 6,
            icon: 'icon-radio',
            type: 'textarea',
            text: '单选框'
          },
          {
            id: 7,
            icon: 'icon-date',
            type: 'textarea',
            text: '日期选择器'
          },
          {
            id: 8,
            icon: 'icon-Timeoutlinedicon',
            type: 'textarea',
            text: '日期选择器'
          },
          {
            id: 9,
            icon: 'icon-rate',
            type: 'textarea',
            text: '日期选择器'
          },
          {
            id: 10,
            icon: 'icon-slider',
            type: 'textarea',
            text: '滑块输入条'
          },
          {
            id: 11,
            icon: 'icon-kaiguankai',
            type: 'textarea',
            text: '开关'
          }
        ],
        selected: [] as SelectedFormItem[],
        showAddVisible: false,
        indexActive: '1'
      });
      return {
        states,
        collapsed: ref(false),

      };
    },
    methods: {
      addCounter(tt) {      
        this.counter.push(tt);
      }


    }

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
    margin: 2% 1%;
    padding: 0;
    border: 1px solid #f4f6fc;

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