<template>
    <div>
        <button class="stop" @click="stop">停止播放</button>
        <div class="imgs">
            <div>点击图片即可播放语音导览</div>

            <div class="once">
                <img class="img" @click="previewImage" src="/static/images/VR/1.png" />
                <p @click="play(dev_src)">投影设备</p>
            </div>

            <div class="once">
                <img class="img" src="/static/images/VR/2.png"/>
                <p>表演厅</p>
            </div>
            
            <div class="once">
                <img class="img" @click="play(dev_src)" src="/static/images/VR/3.png"/>
                <p>中控室</p>
            </div>

        </div>
    </div>

</template>

<style>

.imgs{
    height:580px;
    display:flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.img{
    width: 170px;
    height:120px;
}
.once{
    font-size:15px;
    padding-bottom:40px;
    text-align: center;
}
.stop{
    float:right;
    width:50px;
    height:30px;
}

</style>

<script>
const innerAudioContext = wx.createInnerAudioContext();
export default {
    data(){
        return{
            dev_src:"/static/audio/3.aiff",
            gg:"/static/images/VR/1.png",
            proj:"",
            perf:"",
            cont:""
        }
    },
    methods:{
        play(audio){
            innerAudioContext.src = audio
            innerAudioContext.play()
            },
        stop(){
            innerAudioContext.stop()                                                                                                                                                                                               
        },
        previewImage(e) {
        var current = e.target.src
        console.log(current)
        wx.previewImage({
        current: current, // 当前显示图片的http链接  \  
        })
    } 
    }
    
}
</script>