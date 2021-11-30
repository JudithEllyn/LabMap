<template>
    <div class="total" style="background-image:url(/static/images/bg.png)">

        <div class="img">
            <img class="aa" src="/static/images/exp.png" background-size="cover"/>
        </div>
        
        <div class="button">
            <div class="word">点击可以收听对应语种语音导览</div>

            <picker mode=selector @change="picker_J" class="input" :value="index_J"  :range="types_J">
                <button id="jpn_btn" @click="c" class="word2" >日本語ガイド</button>
            </picker>

            <picker mode=selector @change="picker_E" class="input" :value="index_E"  :range="types_E">
                <button id="eng_btn" class="word" >English guide</button>
            </picker>

            <picker mode=selector @change="picker_C" class="input" :value="index_C"  :range="types_C">
                <button id="chn_btn" class="word">中文导览</button>
            </picker>
         
                <button id="stop"  @click="stop" class="ting">停</button>
               
                </div>

    </div>
</template>

<style>
.word{
  font-family:STXingkai;
  font-size:26px;
  text-align:center;
  padding-bottom:20px;
}

.word2{
  font-family:KaiTi;
  font-size:23px;
  font-weight:bolder;
  text-align:center;
  padding-bottom:20px;
}

.img{
    display:flex;
    flex-direction:row;
    justify-content:center;
    height:300px;
}

.button{
    margin-top:40px;
}

#jpn_btn{
    float:left;
    margin-left:20px;
    width:150px;
    height:50px;
    border-radius: 98rpx;
    background-color:burlywood;
}

#eng_btn{
    padding-left:20px;
    width:150px;
    height:50px;
    border-radius: 98rpx;
    background-color:burlywood;
}

#chn_btn{
    margin-top:20px;
    width:150px;
    height:50px;
    border-radius: 98rpx;
    background-color:burlywood;
}

.ting{
  height:25px;
  width:25px;
  margin-top:0.8rem;
  margin-left:-1rem;
  font-family:STXingkai;
  font-size:30px;
}

#stop{
  margin-top:10px;
  margin-right:20px;
  float:right;
  border-radius:30rem;
  height:60px;
  width:60px;
  background-color:brown;
  border:0;
  vertical-align:middle;
  text-align:center;
  line-height:65px;
}
</style>

<script>
const innerAudioContext = wx.createInnerAudioContext();

export default {
    data() {
        return{
            index_C:"",
            index_E:"",
            index_J:"",
            types_E:["brief introdution","Configuration and functions","operatable experiment","Equipment list"],
            types_C:["简介","配置与功能","可操作的实验类型","设备一览"],
            types_J:["案内書","配置と機能","操作可能な操作タイプ","設備一覧"],
            ad_C:["/static/audio/2.aiff"],
            ad_E:[],
            ad_J:[],
        }

    },
    methods:{
        picker_E(e){
            this.index_E= e.mp.detail.value
            console.log("选项改为："+this.types_E[this.index_E])
        },
        picker_J(e){
            this.index_J= e.mp.detail.value
            console.log("选项改为："+this.types_J[this.index_J])
        },
        picker_C(e){
            this.index_C= e.mp.detail.value
            console.log("选项改为："+this.types_C[this.index_C])
        },

        play(audio){
            innerAudioContext.src = audio
            innerAudioContext.play()
            },
        stop(){
            innerAudioContext.stop()                                                                                                                                                                                               
        }          
},

    watch:{
        index_C:function(newValue,oldValue){
            if(this.index_C!=3)
            {
                console.log(this.ad_C[this.index_C])
                this.play(this.ad_C[this.index_C])
            }
            if(this.index_C==3)
            {
                wx.navigateTo({
                    url: '../part/main'
                })
            }
        },
        index_J:function(newValue,oldValue){
            console.log(this.ad_J[this.index_J])
            this.play(this.ad_J[this.index_J])
        },
        index_E:function(newValue,oldValue){
            console.log(this.ad_C[this.index_C])
            this.play(this.ad_C[this.index_C])
        }

}
    
}
</script>