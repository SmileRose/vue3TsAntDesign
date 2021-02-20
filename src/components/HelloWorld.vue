<template>
  <a-layout>
    <!-- <header> -->
    <a-layout-header style="background: #5aa700; padding: 0" :style="{ position: 'fixed', zIndex: 1, width: '100%' }">
    </a-layout-header>
    <!-- <header> -->
    <a-layout style="{min-height: calc(100vh - 64px)}">
      <a-layout>
        <a-layout-sider class="Rose-slider">
          <left-menu :menuitems="states.json" :collapsed="collapsed" @pushItem="appendFormItem"></left-menu>
        </a-layout-sider>
        <!-- 主体 -->
        <a-layout-content class="Rose-content">
          <div v-if="states.selected.length">
            <Content v-for="item in states.selected" :key="item.id" :text="item.text" :icon="item.icon"
              :type="item.type" :attr="item" @update:appendFormItem="appendFormItem">
            </Content>
          </div>
          <div class="Rose-content" v-else>
            <a-empty :image="simpleImage" />
          </div>
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
  import {
    Empty
  } from 'ant-design-vue';
  import {
    SelectedFormItem
  } from '@/lib/interface';
  import LeftMenu from '@/components/common/LeftMenu';
  import Content from '@/components/common/Content';
  export default defineComponent({
    data() {
      return {
        counter: Array
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
            text: '下拉选择器'
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
      const appendFormItem = (x: any) => {
        console.log(x)
        const obj = {
          id: x.type,
          type: x.type,
          text: x.text
        }
        states.selected.push(obj);
      }
      return {
        states,
        appendFormItem,
        collapsed: ref(false),
      };
    },
    methods: {
      addCounter(tt: string) {
        // states.selected.push()
        // console.log(tt)
        // this.counter.push(tt);
      }
    }
  });
</script>
<style lang="less">
  .Rose-content {
    margin: 64px 20px
  }

  .Rose-slider.ant-layout-sider {
    overflow: auto;
    height: 100vh;
    position: fixed;
    left: 0;
    background: #2e2f34;
    top: 64px
  }

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
</style>