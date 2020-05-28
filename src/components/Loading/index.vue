<template>
  <div class="main">
    <div class="loading">
      <span></span>
      <span></span>
      <span></span>
      <span></span>
      <span></span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Loading'
}
</script>

<style scoped>
.main{
width: 100%;
height: auto;
padding-top: 100px;
}
a{
display: block;
text-align: center;
font-size: 20px;
margin-top: 200px;
}
.loading{
    width: 80px;
    height: 40px;
    margin: 0 auto;
    margin-top:100px;
}
.loading span{
    display: inline-block;
    width: 8px;
    height: 100%;
    border-radius: 4px;
    background: red;
    animation: load 1.04s ease infinite;
    margin-left: 5px;
}
@keyframes load{
    0%,100%{
        height: 40px;
        background: red;
    }
    50%{
        height: 60px;
        margin-top: -20px;
        background: rgb(233, 125, 125);
    }
}
.loading span:nth-child(2){
    animation-delay: 0.13s;
}
.loading span:nth-child(3){
    animation-delay:0.26s;
}
.loading span:nth-child(4){
    animation-delay:0.39s;
}
.loading span:nth-child(5){
    animation-delay:0.52s;
}
</style>
