<template>
   <ol>
        <li v-for="(item, index) in hdata" v-bind:key="item.name">
            <span class="order">{{index + 1}}</span>
            <a href="#" class="avatar"><img v-bind:src="item.img" alt=""></a>
            <div class="textCon">
                <h4>{{item.name}}</h4>
                <p>
                    <span>{{item['read-num']}}</span>
                    <span>{{item['thumb-num']}}</span>
                </p>
            </div>
        </li>
   </ol>
</template>

<script>
    export default{
        props: {
            hdata: Array
        }
    }
</script>

<style>
.box ol{
    padding-top: 20px;
}
.box ol li{
    margin-bottom: 15px;
    padding: 0 8px;
    box-sizing: border-box;
    display: flex;
    align-items: center;
}

.box .order{
    width: 26px;
    height: 15px;
    line-height: 15px;
    text-align: center;
    font-size: 14px;
    color: #333;
}
.box .avatar{
    width: 40px;
    height: 40px;
    margin-right: 6px;
    position: relative;
}
.box li:nth-child(1) .avatar{
    height: 52px;
    background-image: url('https://iknowpc.bdimg.com/static/home/widget/influence/img/first.f968019.png');
    background-size: cover;
}
.box li:nth-child(2) .avatar{
    height: 52px;
    background-image: url('https://iknowpc.bdimg.com/static/home/widget/influence/img/second.8d55242.png');
    background-size: cover;
}

.box li:nth-child(3) .avatar{
    height: 52px;
    background-image: url('https://iknowpc.bdimg.com/static/home/widget/influence/img/third.2079c92.png');
    background-size: cover;
}
.box .avatar img{
    position: absolute;
    bottom: 3px;
    left: 3px;
    width: 34px;
    height: 34px;
    border-radius: 34px;
}
.textCon h4{
    color: #333;
    font-weight: normal;
    font-size: 14px;
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
}
.textCon span{
    margin-right: 3px;
    font-size: 12px;
    color: #666;
}
</style>
