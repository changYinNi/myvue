<template>
    <div class="box">
        <head-vue v-bind:htitle="boxes.title" ></head-vue>
        <list-vue v-bind:hdata="boxes.data"></list-vue>
    </div>
</template>

<script>
import HeadVue from './HeadVue.vue';
import ListVue from './ListVue.vue';

    export default{
        props: {
            boxes: Object
        },
        components: {
            HeadVue,
            ListVue
        }
    };

</script>

<style scoped>
    .box{
        width: 240px;
        height: 400px;
        background: #FFF;
        box-shadow: 0 6px 14px rgba(158,172,182,.25);
        border-radius: 6px;
        overflow: hidden;
        margin: 20px;
    }    
</style>