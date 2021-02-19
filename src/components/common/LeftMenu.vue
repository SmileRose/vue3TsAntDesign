<template>
    <a-layout-sider v-model:collapsed="collapsed" :trigger="null" collapsible style="background:#fff">
        <div class="Rose-lists">
            <!-- 基础字段 -->
            <ul class="Rose-para">
                <li class="Rose-menu-item"><a draggable="false">
                        <StarOutlined />
                        <span>单行文本</span></a>
                </li>
                <li class="Rose-menu-item"><a draggable="false">
                        <StarOutlined />
                        <span>多行文本</span></a>
                </li>
                <li class="Rose-menu-item"><a draggable="false">
                        <StarOutlined />
                        <span>计数器</span></a>
                </li>
                <li class="Rose-menu-item"><a draggable="false">
                        <StarOutlined />
                        <span>单选框组</span></a>
                </li>
                <li class="Rose-menu-item"><a draggable="false">
                        <StarOutlined />
                        <span>多选框组</span></a>
                </li>

                <li class="Rose-menu-item"><a draggable="false">
                        <StarOutlined />
                        <span>下拉选择框</span></a>
                </li>
                <li class="Rose-menu-item"><a draggable="false">
                        <StarOutlined />
                        <span>时间选择器</span></a>
                </li>
                <li class="Rose-menu-item"><a draggable="false">
                        <i></i>
                        <span>日期选择器</span></a>
                </li>
                <li class="Rose-menu-item"><a draggable="false">
                        <i></i>
                        <span>评分</span></a>
                </li>
                <li class="Rose-menu-item"><a draggable="false">
                        <i></i>
                        <span>颜色选择器</span></a>
                </li>

                <li class="Rose-menu-item"><a draggable="false">
                        <i></i>
                        <span>开关</span></a>
                </li>
                <li class="Rose-menu-item"><a draggable="false">
                        <i></i>
                        <span>滑块</span></a>
                </li>
                <li class="Rose-menu-item"><a draggable="false">
                        <i></i>
                        <span>文字</span></a>
                </li>
            </ul>

        </div>
    </a-layout-sider>
</template>
<script lang="ts">
    import {
        defineComponent,
        ref,
        // PropType
    } from 'vue'


    export default defineComponent({
        props: {
            name: String,
            success: {
                type: String
            }          
        },
        setup() {
            //在 setup() 函数中，不需要将类型传递给 props 参数，因为它将从 props 组件选项推断类型。
            return {                
                collapsed: ref(false),
            };
        },

    })

</script>