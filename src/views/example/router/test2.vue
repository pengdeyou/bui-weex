<template>
    <div class="span1 center">
        <text>路由内容test2</text>
        <bui-button type="primary" value="返回" @click="jumpTo"></bui-button>
    </div>
</template>

<style lang="scss" src="src/css/buiweex.scss"></style>


<script>
    const globalEvent = weex.requireModule('globalEvent');
    import buiweex from 'src/js/buiweex.js';
    module.exports = {
        data () {
            return {
            }
        },
        methods: {
            jumpTo() {
                this.$router.go(-1)
            }

        },
    }
</script>



