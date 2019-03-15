<template>
  <div id="app">
    <div class="threeStruc">
      <div class="head">進入真題庫：開始學習</div>
      <div class="part1">
        <div class="part1Struc">
          <Button type="success">閱讀</Button>
          <div class="text">147未達</div>
        </div>
        <div class="part1Struc">
          <Button type="success">聽力</Button>
          <div class="text">57未達</div>
        </div>
        <div class="part1Struc">
          <Button type="success">口語</Button>
          <div class="text">13未達</div>
        </div>
        <div class="part1Struc">
          <Button type="success">寫作</Button>
          <div class="text">0未達</div>
        </div>
      </div>
    </div>

    <div class="threeStruc">
      <div class="head">我的學習進度</div>
      <div class=part2>
        <div class="part2Struc">
          <div class="text">閱讀</div>
          <img class="canvas" src="./assets/canvas.jpg"/>
          <div class="text">剩余:28天21小时3分钟</div>
          <div @click="changeTime" class="changeTime"><Icon type="md-create" />更改开启时间</div>
        </div>
        <div class="part2Struc">
          <div class="text">聽力</div>
          <img class="canvas" src="./assets/canvas.jpg"/>
          <div class="text">2019年1月21日开始</div>
          <div @click="changeTime" class="changeTime"><Icon type="md-create" />更改开启时间</div>
        </div>
        <div class="part2Struc">
          <div class="text">口語</div>
          <img class="canvas" src="./assets/canvas.jpg"/>
          <div class="text">2019年1月21日繼續</div>
          <div @click="changeTime" class="changeTime"><Icon type="md-create" />更改开启时间</div>
        </div>
        <div class="part2Struc">
          <div class="text">寫作</div>    
          <div class="noWork">無學習進度</div>
          <div class="text">2019年1月21日开始</div>
          <div @click="changeTime" class="changeTime"><Icon type="md-create" />更改开启时间</div>
        </div>
      </div>
    </div>

    <div class="threeStruc">
      <div class="head">我的作業批改</div>
      <div class="part3">

        <div v-if="SRflag" @click="DLspeakingRevised" class="DLbtn">
          <div id="DLtext">下載口語批改</div>
          <Icon id="DLicon" type="md-download" size="20"/>
        </div>
        <Button v-else>無口語批改</Button>

        <div v-if="WRflag" @click="DLwritingRevised" class="DLbtn">
          <div id="DLtext">下載寫作批改</div>
          <Icon id="DLicon" type="md-download" size="20"/>
        </div>
        <Button v-else>無寫作批改</Button>

        <div class="DLbtn"></div>
        <div class="DLbtn"></div>

      </div>
    </div>

    <div class="threeStruc">
      <div class="head">我的筆記</div>
      <div class="part4">

        <div v-if="RNflag" @click="DLreadingNote" class="DLbtn">
          <div id="DLtext">下載閱讀筆記</div>
          <Icon id="DLicon" type="md-download" size="20"/>
        </div>
        <Button v-else>無閱讀筆記</Button>

        <div v-if="LNflag" @click="DLlisteningNote" class="DLbtn">
          <div id="DLtext">下載聽力筆記</div>
          <Icon id="DLicon" type="md-download" size="20"/>
        </div>
        <Button v-else>無聽力筆記</Button>

        <div v-if="SNflag" @click="DLspeakingNote" class="DLbtn">
          <div id="DLtext">下載口語筆記</div>
          <Icon id="DLicon" type="md-download" size="20"/>
        </div>
        <Button v-else>無口語筆記</Button>

        <div v-if="WNflag" @click="DLwritingNote" class="DLbtn">
          <div id="DLtext">下載寫作筆記</div>
          <Icon id="DLicon" type="md-download" size="20"/>
        </div>
        <Button v-else>無寫作筆記</Button>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'app',
  data(){
    return{
      SRflag : true,
      WRflag : false,
      WNflag : true,
      SNflag : false,
      RNflag : true,
      LNflag : true,
    };
  },

  methods:{
    changeTime(){
      this.$Message.success('Change open time successfully!');
    },
    DLspeakingRevised(){
      this.$Message.success('Speaking results download successfully!');
    },
    DLwritingRevised(){
      this.$Message.success('Writing results download successfully!');
    },
    DLreadingNote(){
      this.$Message.success('Reading note download successfully!');
    },
    DLlisteningNote(){
      this.$Message.success('Listening note download successfully!');
    },
    DLspeakingNote(){
      this.$Message.success('Speaking note download successfully!');
    },
    DLwritingNote(){
      this.$Message.success('Writing note download successfully!');
    },
  }
}

</script>

<style>

.threeStruc {
  width: 1170px;
  margin: 0 auto;
}
.part1Struc{
  margin:0 auto;
}
.part2Struc{
  margin:0 auto;
  width : 200px;
}
.head{
  border-bottom: 1px solid gray;
  font-weight: bolder;
  font-size: 20px;
  margin: 10px;
}
.canvas{
  display : flex;
  justify-content: center;
  align-items: center;
  width: 180px;
  height: 180px;
  margin: 0 auto;

} 
.noWork {
  display : flex;
  justify-content: center;
  align-items: center;
  width:180px;
  height:180px;
  font-size: 27px;
  margin: 0 auto;
}
.text {
  text-align: center;
  font-size: 18px;
}
.changeTime {
  margin:20px auto;
  width: 115px;
  text-align: center;
  color: #4B86D5 ;
  border-bottom: 1px solid #4B86D5;
  font-size: 16px;
  cursor : pointer;
}
.part1 {
  display: flex;
  justify-content: center;
  align-items: center;
}
.part1 Button{
  width : 120px;
  font-weight : border;
  font-size: 18px;
  margin-top: 20px;
}
.part1 .text {
  width:fit-content;
  margin-top: 20px;
  margin-bottom: 10px;
  margin-left: auto;
  margin-right: auto;
  border-bottom: 1px dotted rgba(16, 16, 16, 0.65);
}
.part2 {
  display: flex;
  justify-content: center;
  align-items: center;
}
.part2 .text{
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 20px;
  margin-bottom: 10px;
}
.part3 {
  display: flex;
  
}

.part3 .DLbtn{
  display: flex;
  margin: 30px auto;
  width: 130px;
  height: 31px;
  cursor: pointer;
}
.part3 Button{
  width: 130px;
  height: 31px;
  margin: 30px auto;
}
.part4 {
  display: flex;
  justify-content: center;
  align-items: center;
}
.part4 .DLbtn{
  margin:30px auto;
  display: flex;
  cursor:pointer;
}
.part4 Button{
  margin:0 auto;
  width: 130px;
  height: 31px;
}
#DLicon{
  display: flex;
  justify-content: center;
  align-items: center;
  width: 25px;
  height: 31px;
  background: #4DAF80;
  
}
#DLtext {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 105px;
  height: 31px;
  background: #CBEADB;
}

</style>
