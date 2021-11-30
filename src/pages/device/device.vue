<template>

<div style="background-image: url(/static/images/blue4.png)">
<div class="title" >{{tit1}}</div>
<div style="float:right;clear:both;" align="center">
<img class="a" src="/static/images/exp.png" background-size="cover"/>
</div>

<div class="message">{{msg1}}</div>
<button id="chn_btn" @click="index_E" class="message3">汉语介绍</button>
    <button id="stop_btn" @click="stop" class="message3">停</button>

<div class="title" >{{tit2}}</div>
<div class="message">{{msg2}}</div>
<button id="eng_btn" @click="index_E" class="message3">English guide</button>
    <button id="stop_btn" @click="stop" class="message3">stop</button>


<img class="aa" src="/static/images/com.png" background-size="cover"/>
<div class="title2" >{{tit3}}</div>
<div class="message2">{{msg3}}</div>
<div class="message2">{{msg4}}</div>
<button id="jpn_btn" @click="index_J" class="message4">日本語ガイド</button>
    <button id="stop_btn" @click="stop" class="message3">停</button>

</div>
</template>

<script>
import card from '@/components/card'
const innerAudioContext = wx.createInnerAudioContext();
export default {
  data () {
    return{
      tit1:'实验室概况',
      msg1:'目前，中心建筑面积约4360平方米，9种类型39套立体虚拟仿真实验室、立体远程训练实验室、立体协同训练仿真实验室、立体化虚拟个性化实验室等，3套无线调频及音频外文广播电台、图书资料室2个、集中控制室3套，设备3900余台件，固定资产达4320万元。承担全校9个学院，两个研究生院本科及研究生公共基础实验教学工作，现为全校36个本科专业42个研究生专业开设44门实验课程，是我校规模最大的基础实践教学平台，每年直接受益学生达12000余名，年实验人时数超过78万，是为社会培养适应信息化时代发展需要的复合型人才的重要基地，逐步形成了实验装备先进、实验体系完善、实验队伍优秀、管理规范高效、创新氛围浓厚、具有国内领先水平、特色鲜明的虚拟仿真实验教学中心。',
      tit2:'The introduction of labs',
      msg2:'So far, the centre consists of 9 types of 39 sets of three-dimensional virtual simulation laboratory, three-dimensional tele-training laboratory, three-dimensional coordination training simulation laboratory, three-dimensional simulation personalization laboratory, etc, with a floorage of 4360 square metre. As well as 3 sets of wireless FM and audio English broadcasting station, 2 reference rooms, 3 centralized control rooms,more than 3900 pieces of equipment.The fixed asset of the centre is now 43.2 million yuan. As the largest basic practical teaching platform, the centre undertakes the public basic experimental teaching work of 9 colleges and 2 graduate schools, launches 44 experimental courses for 36 undergraduate majors and44 postgraduate majors, which benefits more than 12 thousand students annually while more than 780,000 experiment hours every year. As a significant base to cultivate inter-disciplinary talents adapting the development of informationization for society, it has gradually formed a virtual simulation experimental teaching centre with advanced experiment equipment, perfect experiment system, excellent experiment team, productive specification management, creative atmosphere and domestic advanced level.',
      tit3:'実験室概要',
      msg3:'現在、建築面積約4360平方メートル、9种类、39セットの立体バーチャルリアリティーラボラトリ、立体リモート練習ラボラトリ、立体協同練習バーチャルリアリティーラボラトリ、立体個性的なバーチャルリアリティーラボラトリなどがある。3軒無線fmやオーディオの放送部門、図書資料室2つ、コンソール3軒、設備約3900台があり、固定資産4320万元。ラボラトリは全校の9つの学部、２つの大学院の全体学生の基礎実験教学のため設立したものである。ラボラトリは現在全校36個の学部の専門と大学院の42個の専攻、合わせて44門の実験の課程のため開設されて、我が校の最大規模の基礎実践教学のプラットフォームである。毎年直接受益の生徒約12000万人、年実験に参加する人',
      msg4:'学生数は78万を超える。我がラボラトリは情報化時代の高速な発展に応じる複合型の人材を育てる重要基地で、実験設備先進、実験システム完備、実験チーム優秀、管理高効、革新的な雰囲気が濃厚の、国内のトップレベル、特色の鮮やかなバーチャルリアリティー教育センターである。',
      }
  },
  methods:{
  
play(audio){
            innerAudioContext.src = audio
            innerAudioContext.play()
            },
stop(){
            innerAudioContext.stop()                                                                                                                                                                                               
      },        

index_E(){
          console.log("/static/audio/an.mp3")
          this.play("/static/audio/an.mp3")
        },
           
        
index_J(){
          console.log("/static/audio/an.mp3")
          this.play("/static/audio/an.mp3")
        },
index_C(){
            console.log("/static/audio/an.mp3")
            this.play("/static/audio/an.mp3")
            }
   }

}
</script>

<style >
.title{
  color:rgb(3, 92, 3);
  font-size:25pt;
  font-family:'STXingkai';
  text-align:center; 
  font-weight:bold;
  padding:20rpx;
}
.title2{
  color:rgb(3, 92, 3);
  font-size:25pt;
  font-family:'KaiTi';
  text-align:center; 
  font-weight:bold;
}
.message{
  color:black;
  font-family: 'STXingkai';
  font-weight: bold;
  text-indent:2em;
  padding:10px;
}
.message2{
  color:black;
  font-family:'KaiTi';
  font-weight:900;
  text-indent:2em;
  padding:10px;
}

.message3{
  color:black;
  font-size:20pt;
  font-family: 'STXingkai';
  font-weight: bold;
  padding:10px;
}
.message4{
  color:black;
  font-family:'KaiTi';
  font-weight:900;
  font-size:20pt;
  padding:10px;
}

.aa{
  display: flex;
  justify-content:center;
  align-items: center;
  width:800rpx;
  height:400rpx;
  margin:10px,10px,10px,10px;
}
.a{
  width:450rpx;
  height:450rpx;
  border-radius:50%;
  overflow:hidden;
  justify-content:center;
  text-align:center
}

#jpn_btn{
    float:left;
    margin-left:20px;
    width:150px;
    height:50px;
    border-radius: 98rpx;
    background-color:burlywood;
    border:0;
    vertical-align:middle;
    text-align:center;
    line-height:20px;
}

#eng_btn{
    float:left;
    margin-left:20px;
    width:150px;
    height:50px;
    border-radius: 98rpx;
    background-color:burlywood;
    border:0;
    vertical-align:middle;
    text-align:center;
    line-height:15px;
}

#chn_btn{
    float:left;
    margin-left:20px;
    width:150px;
    height:50px;
    border-radius: 98rpx;
    background-color:burlywood;
    border:0;
    vertical-align:middle;
    text-align:center;
    line-height:35px;
}

#stop_btn{
  float:right;
  margin-right: 20px;
  width:150px;
  height:50px;
  border-radius: 98rpx;
  background-color:burlywood;
  border:0;
  vertical-align:middle;
  text-align:center;
  line-height:35px;
}

</style>    