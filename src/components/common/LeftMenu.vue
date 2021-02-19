<template>
    <a-layout-sider v-model:collapsed="collapsed" :trigger="null" collapsible style="background:#fff">
        <div class="Rose-lists">
            <!-- 基础字段 -->
            <div class="Rose-para">
                <a-button v-for="(item, key, index) in state.json" v-bind:key="key" class="Rose-menu-item"
                    @click="addItem(item.type)">
                    {{item.text}}
                </a-button>
            </div>

        </div>
    </a-layout-sider>
</template>
<script lang="ts">
    import {
        defineComponent,
        ref,
        reactive,
        PropType
    } from 'vue'


    export default defineComponent({
        props: {
            name: String,
            states: {
                type: Object
            }
        },

        components: {

        },
        setup() {
            //在 setup() 函数中，不需要将类型传递给 props 参数，因为它将从 props 组件选项推断类型。

            const state = reactive({
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
            })
            return {
                state,
                collapsed: ref(false),
            };
        },
        methods: {
            addItem(thisType: string) {             
                this.$emit("pushItem", thisType)
            }
        }
    })
</script>