<template>
<div style="background-image: url(/static/images/bg.png)">
    <div class="title" >{{tit1}}</div>
    <div class="message">{{msg1}}</div>
        <img class="a" src="/static/images/bupt.jpg" background-size="cover"/>
    <div class="message">{{msg2}}</div>
    <div class="message">{{msg3}}</div>
    <div class="message">{{msg4}}</div>
    <div class="message">{{msg5}}</div>

    <div>
     
        <button id="chn_btn" @click="index_C" class="message3">汉语介绍</button>
        <button id="stop_btn" @click="stop" class="message3">停</button>

    </div>
    <div class="title" >{{tit2}}</div>
    <div class="message">{{msg6}}</div>
    <div class="message">{{msg7}}</div>
    <div style="float:right;clear:both;" align="center">
    <img class="aa" src="/static/images/renwen.jpg" background-size="cover"/>
    </div>
    <div class="message">{{msg8}}</div>
    <div class="message">{{msg9}}</div>
    <div class="message">{{msg10}}</div>

        <button id="eng_btn" @click="index_E" class="message3">English guide</button>
        <button id="stop_btn" @click="stop" class="message3">stop</button>

    <div class="title2" >{{tit3}}</div>
    <div class="message2">{{msg11}}</div>
    <div class="message2">{{msg12}}</div>
    <div style="float:left;clear:both;" align="center">
      <img class="aa" src="/static/images/fazhan.jpg" background-size="cover"/>
    </div>
    <div class="message2">{{msg13}}</div>
    <div class="message2">{{msg14}}</div>
    <div class="message2">{{msg15}}</div>

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
      tit1:'发展历程',
      msg1:'北京邮电大学是一所以信息科技为特色、工学门类为主体，工管文理相结合的多科性大学。',
      msg2:'长期以来，我校以培养高素质创新人才为宗旨，深化语言实验教学改革，1980年，我校建立了当时国内最先进的语言实验室，1998年，成立了语言实验教学中心，为了满足专业及教师需要，还建设语言情景创意实验室、语言测试实验室。' ,
      msg3:'2002年，为进一步落实教育部“加强实用性英语教学，提高语言综合能力”这一国家发展战略，扩建了专门用于语言课堂教学研究和创新性实验教学的实验室，先后建立了开放式数字网络语言实验室、语音智能实验室、网络自主学习中心。',
      msg4:'2008年，中心又整合了语言技能训练实验室、中美实时语言互动实验室，2010年建立虚拟仿真实验室，实现学科深度交叉融合的虚拟仿真实验平台，同时全面开展立体网络协同仿真教学模式，满足不同层次学生的教学需要。',
      msg5:'我校先后获得“国家级精品课程”、“北京市优秀教学团队”等称号，并成为教育部示范院校、北京市高等学校实验教学示范中心、北京市大学英语实验教学创新实践基地、国家级实验教学示范中心。',
      tit2:'The history of development',
      msg6:'Beijing University of Posts and Telecommunication is a multidisciplinary university featuring information technology and engineering, which is composed of engineering, management, humanities and natural science.',
      msg7:'Our school has long aimed at cultivating high-quality innovative talents, deepened the reform of language experiment and teaching.We established the most advanced laboratory in China in 1980.We established language experiment and teaching centre in 1998, the language situational creative laboratory and the language testing laboratory as well so as to satisfy the needs of subjects and teaching.',
      msg8:'In 2002, the centre enlarged the laboratory specialized in the research on language class teaching and innovative experimental teaching in order to further implement the Ministry of Education’s national development strategy of ‘Strengthening practical English teaching and improving the synthetical ability of language’. Our school successively established open digital network laboratory, intelligent voice laboratory, and online autonomous learning centre.',
      msg9:'The centre integrated language skills training laboratory and China-The United States real-time interactive language laboratory in 2008. The centre established Virtual Simulation Laboratory achieving the virtual simulation platform of deep cross-fusion of subjects in 2010, meanwhile, overall carried out three-dimensions network cooperative simulation teaching model to satisfy teaching needs of different layers of students.',
      msg10:'Our school successively obtained the titles of ‘National Excellent Courses’, ’Beijing Excellent Teaching Team’, and became the Ministry of Education’s model college, Beijing University Experimental Teaching Demonstration Center, Beijing college English experimental teaching innovative practical base, and nation-level experimental teaching demonstration centre.',
      tit3:'発展の過程。',
      msg11:'北京郵電大学は、情报科学技术を特色とし、工学系を主体とし、管理学、文系と理系を组み合わせた多科性大学である。',
      msg12:'長年、わが校は革新人材を養成するという宗旨で、語学の教育改革を進めている。1980年、わが校は当時国内最先端の言語のラボラトリを設立した。1998年、言語教育センターを設立し、課程や教師の需要を満たすため、新コンセプトラボラトリは、言語テストラボラトリを創立した。',
      msg13:'2002年、文部省の「実用の英語の授業を強化し、言語総合能力を高める」という国家発展戦略に応じて、言語の教学研究と革新的な実験教学に専用の実験室を拡張し、オープン型デジタルネットワーク言語実験室、音声インターアクション実験室、ネットワーク自主学習センターを相次いで設立した。',
      msg14:'2008年、言語技能訓練センターや中米言語リアルタイムインターアクションを統合した。2010年にバーチャルリアリティーラボラトリを設立したため、各学科の深い交差融合ができた。',
      msg15:'同時、ネットワーク協同シミュレーション授業が実現し、レベルの違う学生たちの需要を満たした。「国家級精品課程」、「北京市優秀教学チーム」などの称号を次々に取得し、文部省のモデルスクール、北京市高等学校実験教学センター、北京市大学英語実験教学革新実践基地、国家級実験教学センターとなった。',
     
            
          
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
            this.play("/static/audio/1.aiff")
            }
  }
}
</script>

<style>

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
  padding:20rpx;
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
.a{
  display: flex;
  justify-content:center;
  align-items: center;
  width:800rpx;
  height:400rpx;
  margin:10px,10px,10px,10px;
}

.aa{
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