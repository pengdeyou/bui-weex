<template>
    <div class="center">
        <bui-image src="/image/logo.png" width="150px" height="150px"></bui-image>
        <text class="h2">BUI-Weex</text>
        <text class="h4">专注为Weex前端开发者提供高质量UI组件</text>
        <bui-button type="primary" value="快速体验" @click="jumpTo"></bui-button>
    </div>
</template>

<style lang="scss" src="src/css/buiweex.scss"></style>

<script>
    const globalEvent = weex.requireModule('globalEvent');
    module.exports = {
        data () {
            return {
                size: 60
            }
        },
        methods:{
            jumpTo () {
                var url = "index.js";
                this.$push(url);
            }
        },
        mounted () {
            globalEvent.addEventListener("androidback", (e)=> {
                this.$pop();
            });
        }
    }
</script>