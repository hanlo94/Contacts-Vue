<template>
  <div id="app">

    <my-header class="header-bar fixed">
        <button slot="left" class="leftButton">退出</button>
        <p> {{msg}} </p>
        <button slot='right' class="rightButton">主页</button>
    </my-header>

    <div class="container">

      <ul class="userIndex-Group">
        <li v-for="item in userData" class="userIndex-Item">
          <p class="itemName">{{ item.group}}</p>
          <ul class="itemList">
            <li v-for="member in item.users " class="itemList-Member">{{ member.user +'   '+ member.tel }}</li>
          </ul>
        </li>
      </ul>
      <ul class="sideBarMenu">

        <li @click="scrolltoIndex" v-for="index in userData">{{ index.group}}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data(){
    return {
      msg: '通讯库',
      userData:userData,
    }
  },
  components:{
    'my-header':myHeader
  },
  methods:{
    scrolltoIndex:function(e){
      console.log(e.target,e.target.classList,'\n',e.target.nodeName,'\n');
      var nodes=document.getElementsByClassName('itemName');
      for(let i = 0;i < nodes.length;i++){
        if(e.target.innerText === nodes[i].innerText ){
          console.log(i);
          // nodes[i].setAttribute()
        }
      }

    }
  }
}
var myHeader = {
  template:` <div>
      <slot name="left"></slot>
       <slot></slot>
      <slot name="right"></slot>
    </div>
  `
}

const userData = [
  {
    key:"0", group:"A", users:[
      {key:"01",user:"a1",tel: "17858804441"},
      {key:"02",user:"a2",tel: "17858804442"},
      {key:"03",user:"a3",tel: "17858804443"},
      {key:"04",user:"a4",tel: "17858804444"},
      {key:"05",user:"a5",tel: "17858804445"}]
  },
  {
    key:"1", group:"B", users:[
      {key:"01",user:"b1",tel:"17858804441"},
      {key:"02",user:"b2",tel:"17858804442"},
      {key:"03",user:"b3",tel:"17858804443"},
      {key:"04",user:"b4",tel:"17858804444"},
      {key:"05",user:"b5",tel:"17858804445"}]
  },
  {
    key:"2", group:"C", users:[
      {key:"01",user:"c1",tel:"17858804441"},
      {key:"02",user:"c2",tel:"17858804442"},
      {key:"03",user:"c3",tel:"17858804443"},
      {key:"04",user:"c4",tel:"17858804444"},
      {key:"05",user:"c5",tel:"17858804445"}]
  },
  {
    key:"3", group:"D", users:[
      {key:"01",user:"d1",tel:"17858804441"},
      {key:"02",user:"d2",tel:"17858804442"},
      {key:"03",user:"d3",tel:"17858804443"},
      {key:"04",user:"d4",tel:"17858804444"},
      {key:"05",user:"d5",tel:"17858804445"}]
  },
  {
    key:"0", group:"E", users:[
      {key:"01",user:"e1",tel:"17858804441"},
      {key:"02",user:"e2",tel:"17858804442"},
      {key:"03",user:"e3",tel:"17858804443"},
      {key:"04",user:"e4",tel:"17858804444"},
      {key:"05",user:"e5",tel:"17858804445"}]
  },
  {
    key:"0", group:"F", users:[
      {key:"01",user:"f1",tel:"17858804441"},
      {key:"02",user:"f2",tel:"17858804442"},
      {key:"03",user:"f3",tel:"17858804443"},
      {key:"04",user:"f4",tel:"17858804444"},
      {key:"05",user:"f5",tel:"17858804445"}]
  }
]
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/*reset*/
ul,li{
  list-style-type: none;
  margin:0;
  padding:0;
  display: block;
}
p {
  margin: 0;
}
#app {
  width: 100%;
  max-width: 600px;
  margin: auto;
  background:#606266;
}
.fixed{
  position: fixed;
 }
.container {
   padding-top: 60px;
  position: relative;
}
.header-bar {
  width: 100%;
  max-width: 600px;
  height: 60px;
  line-height: 60px;
  margin: auto;
  background: #3a8ee6;
  display: flex;
  justify-content: space-between;
  font-size:20px;
  color:#eee;
  z-index: 10;
}
.leftButton {
  height: 30px;
  width: 60px;
  background: transparent;
  border: none;
  font-size: 18px;
  transform: translate(0%,50%);
  outline:none;
}
.rightButton {
  height: 30px;
  width: 60px;
  background: transparent;
  border: none;
  font-size: 18px;
  transform: translate(0%,50%);
  outline:none;

}

ul.userIndex-Group {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  background: whitesmoke;
}
li.userIndex-Item {
  text-align: left;
  width: 100%;
}
ul.itemList {
}
li.itemList-Member {
  padding: 10px;
  background:#8cc5ff;

}
p.itemName {
  margin: 10px 0 5px 0 ;
}
.sideBarMenu {
  right: 6px;
  top: 10%;
  width: 40px;
  text-align: right;
  position: fixed;
}
.sideBarMenu li {
  margin:5px 0;
  background: transparent;
  /*border: 1px solid #00ffff;*/
  height: 30px;
  line-height: 30px;
  font-size: 17px;
}
a {
  color: #42b983;
}
</style>
