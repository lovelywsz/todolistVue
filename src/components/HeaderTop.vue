<template>
  <div class="headerTop">
    <img src="../assets/images/avatar.jpg">
    <h1>{{ msg }}</h1>
    <p>{{ content }}</p>
  </div>
</template> 

<script>
export default {
  name: 'headerTop',
  data () {
    return {
      msg: 'COCO WANG',
      content: 'move forward relentlessly'
    }
  }
}
</script>

<style>
.headerTop{
  background:url(../assets/images/bg.jpg) top left  no-repeat;
  background-size:contain;
  border-radius: 4px 4px 0 0;
  overflow:hidden;
  zoom:1;
  text-align:center;
}
.headerTop img{
  padding: 2px;
  line-height: 1.52857143;
  background-color: #e1e2e3;
  border: 1px solid #e1e2e3;
  border-radius: 3px;
  -webkit-transition: all 0.2s ease-in-out;
  -o-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  display: block;
  width: 120px;
  height: 120px;;
  border-radius: 50%;
  margin:40px auto 10px;
  box-sizing:border-box;
}
.headerTop h1{font-size:20px;color:#515253;}
.headerTop p{font-size:14px;color:#909FA7;line-height:22px;}
</style>
