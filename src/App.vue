<template>
<div>
    <mt-header title="页面标题" v-if="visible">
        <router-link to="/" slot="left">
            <mt-button icon="back">返回</mt-button>
        </router-link>
        <mt-button icon="more" slot="right"></mt-button>
    </mt-header>
    <router-view></router-view>
</div>
</template>

<style>
@reset-global mobile;

html,
body {
    background-color: #fafafa;
    -webkit-overflow-scrolling: touch;
    user-select: none;
}

a {
    color: inherit;
}

.page-back {
    display: inline-block;
    position: absolute 12px * * 10px;
    width: 40px;
    height: 40px;
    text-align: center;
    i {
        font-size: 24px;
        line-height: 40px;
    }
}
</style>

<script type="text/babel">

export default {
    computed: {
        visible() {
            return ['/', '/header', '/search'].indexOf(this.$route.path) < 0;
        }
    }
};
</script>
