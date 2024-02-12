<template>
    <h3>{{htitle}}</h3>
</template>

<script>
    export default{
        props: {
            htitle: String
        }
    }
</script>

<style>
box h3{
    height: 57px;
    padding-left: 16px;
    box-sizing: border-box;
    font-size: 18px;
    color: #FFF;
    line-height: 57px;
}
.box:nth-child(1) h3{
    background-image: url('https://iknowpc.bdimg.com/static/home/widget/influence/img/greenBg.1bf0e22.png');
}
.box:nth-child(2) h3{
    background-image: url('https://iknowpc.bdimg.com/static/home/widget/influence/img/orangeBg.edc7767.png');
}
.box:nth-child(3) h3{
    background-image: url('https://iknowpc.bdimg.com/static/home/widget/influence/img/blueBg.d0ed0e3.png');
}
</style>