<template>
    <div>
        <bui-header
                title="弹出框(bui-dialog)"
                :leftItem="leftItem"
                @leftClick="back">
        </bui-header>

        <div class="center" style="padding:10px;">
            <bui-button type="warning" value="打开自定义窗口" @click="open"></bui-button>
        </div>

        <bui-dialog v-model="showDialog" @btnClick="onDialogCallback">
            <text>欢迎使用BUI-Weex!</text>
            <text>基于weex构建的一套高质量UI框架</text>
        </bui-dialog>
    </div>
</template>

<style lang="scss" src="src/css/buiweex.scss"></style>

<script>
    export default {
        data: function(){
            return {
                leftItem: {
                    icon: 'ion-chevron-left'
                },
                showDialog: false
            }
        },
        methods: {
            back() {
                this.$pop();
            },
            open() {
                this.showDialog = true;
            },
            onDialogCallback (text) {
                this.showDialog = false;
                this.$toast(text)
            }
        }
    }
</script>