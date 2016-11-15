<template>
  <div id="app">
    <header-top msgfromF='code by coco'></header-top>
    <div class='inputWrap'>
      <label for='info'>TO DO LIST:</label>
      <input id='info' v-model='newItem' v-on:keyup.enter='addNew'>
    </div>
    <do-list v-bind:listItem='items'></do-list>
  </div>
</template>

<script>
import Store from './store'
import HeaderTop from './components/HeaderTop'
import DoList from './components/DoList'
export default {
  name: 'app',
  components: {
    HeaderTop,
    DoList
  },
  data () {
    return {
      items:Store.fetch(),
      newItem:''
    }
  },
  methods:{
    addNew:function(){
      this.items.push({
        label:this.newItem,
        isFinished:false
      })
      this.newItem = ''
    }
  },
  watch:{
    items:{
      handler:function(items){
        Store.save(items)
      },
      deep:true
    }
  }
}
</script>

<style>
body{background:#e8eef2;}
#app {
  width:36%;
  margin:5% auto;
  padding-bottom:20px;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  margin-bottom: 21px;
  background-color: #fff;
  border: 1px solid transparent;
  border-radius: 4px;
  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
  box-sizing:border-box;
}
.inputWrap{width:90%;margin:10px auto;}
.inputWrap input{
  box-sizing: border-box;
  width: 76%;
  height: 37px;
  padding: 7px 18px;
  font-size: 14px;
  line-height: 1.52857143;
  color: #3a3f51;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 4px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
}

@import './assets/css/reset.css'
</style>
