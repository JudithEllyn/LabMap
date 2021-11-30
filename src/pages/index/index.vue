<template>
<div class="page">
    <div class="title">
        <p>北京邮电大学</p>
        <p>国家级语言教学实验示范中心</p>
        <div class="img">
            <img :src="logo"/>
        </div>
        <div class="button">
            <button id="dvl_btn" @click="to_dvl">发展历程</button>
            <button id="dvc_btn" @click="to_dvc">实验室概况</button>
            <button id="cons_btn" @click="to_cons">建设概况</button>
        </div>

    </div>
</div>
</template>

<style>
.title{

    font-family: STXingkai;
    font-size:25px;
    text-align:center;
    text-shadow: 4px,4px,4px,green;
    line-height:30px;
}
.img{
    height:300px;
}

.button{
    margin-top:40px;
}

#dvl_btn{
    float:left;
    margin-left:20px;
    width:150px;
    height:50px;
}

#dvc_btn{
    padding-left:20px;
    width:150px;
    height:50px;

}

#cons_btn{
    margin-top:20px;
    width:150px;
    height:50px;

}

</style>

<script>
export default {
    data(){
        return{
            logo:'/static/images/logo.jpg'
        }
    },
    methods:{
        to_dvl(){
            const url='../develop/main'
            wx.navigateTo({url})
        },
        
        to_dvc(){
            const url='../device/main'
            wx.navigateTo({url})
        },
        
        to_cons(){
            const url='../constru/main'
            wx.navigateTo({url})
        }
    }
}
</script>>

