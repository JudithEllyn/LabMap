<template>
    <div class="total">
        <div class="map"><img class="img" src="/static/images/map.jpg"/></div>
        <div class="vr">
            <img class="ins_icon" @click="to_vr" :src="ins_icon"/>
            <img class="icon" v-if="vr"  :src="stat"/>
        </div>
        <div class="ls">
            <img @click="to_ls" class="ins_icon" :src="ins_icon"/>
            <img   v-if="ls" class="icon" :src="stat" />
        </div>
        <div class="init">
            <img class="ins_icon" v-if="init" :src="stat">
        </div>
    </div>
</template>

<style>
.total{
}

.map{
    position:absolute;
    top:20px;
    z-index: -1;
}

.img{
    height:500px;
    weight:300px;
}
.ls{
    position:absolute;
    top:40px;
    left:50px;
    z-index: 2;
}

.vr{
    position:absolute;
    bottom:50px;
    left:80px;
    z-index: 1;
}

.icon{
    padding-left:20px;
    height:30px;
    width:30px;
}

.ins_icon{
    height:20px;
    width:20px;
    padding-left:5px;
    float:left;
}

.init{
    position:absolute;
    bottom:20px;
    margin-top:300px;
    margin-left:180px;
}
</style>

<script>
export default {
    data(){
        return{
            vr:true,
            ls:true,
            init:true,
            ins_icon:"/static/images/Bulb.png",
            stat:"/static/images/arrow.png"
        }
    },
    methods:{
        to_vr(){
            wx.navigateTo({
                url: '../scene_sp/main',
            })
        }
    },
    watch:{


    }
}
</script>