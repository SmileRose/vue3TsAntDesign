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
        PropType
    } from 'vue'


    export default defineComponent({
        props: {
            name: String,
            success: {
                type: String
            },
            callback: {
                type: Function as PropType < () => void >
            },
            message: {
                type: Object as PropType < ComplexMessage > ,
                required: true,
                validator(message: ComplexMessage) {
                    return !!message.title
                }
            }
        },
        // components: {

        // },
        setup() {
            return {
                selectedKeys: ref(['1']),
                collapsed: ref(false),
            };
        },


        // 已启用类型推断
    })


    // import {  Prop } from 'vue-class-component';



    // @Component
    // export default class AlertComponent extends Vue {
    //   // props
    //   @Prop({ default: "这是个弹窗" }) private content!: string;

    //   @Prop({ default: "确定" }) private define!: string;

    //   @Prop({ default: "取消" }) private cancel!: string;

    //   @Prop() private defineHandler: (() => void) | undefined;

    //   @Prop() private cancelHandler: (() => void) | undefined;

    //   // methods
    //   @Emit("define-event")
    //   private defineEvent() {
    //     console.log("点击了确认按钮");
    //   }

    // }
</script>