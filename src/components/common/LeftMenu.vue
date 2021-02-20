<template>
    <a-layout-sider v-model:collapsed="collapsed" :trigger="null" collapsible style="background:#fff">
       
            <!-- 基础字段 -->
            <li class="Rose-para">
                
                <a-button v-for="(item, key, index) in menuitems" v-bind:key="key" class="Rose-menu-item"
                    @click="addItem(item)">
                    {{item.text}}
                </a-button>
            </li>

     
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
            menuitems: {
                type: Object
            }
        },

        components: {

        },
        setup() {
            //在 setup() 函数中，不需要将类型传递给 props 参数，因为它将从 props 组件选项推断类型。

           
            return {              
                collapsed: ref(false),
            };
        },
        methods: {
            addItem(thisType: string) {   
                console.log(thisType)          
                this.$emit("pushItem", thisType)
            }
        }
    })
</script>