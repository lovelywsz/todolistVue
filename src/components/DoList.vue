<template>
  <ul class="doList">
    <li v-for='item in items' v-bind:class='{finished:item.isFinished}' v-on:click='toggleFinish(item)'>
      {{item.label}}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'DoList',
  props:['listItem'],
  data () {
    return {
      items:this.listItem
    }
  },
  methods:{
    toggleFinish:function(item){
      item.isFinished = !item.isFinished
    }
  }
}
</script>

<style>
.finished{
  text-decoration:line-through;
  color:#f00;
}
.doList{margin:30px 25px;list-style:circle inside}
.doList li{
  color:#656565;
  font-size:16px;
  line-height:20px;
}

</style>
