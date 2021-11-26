<template>
  <div class="disc">
      <img :src="details.poster" :alt="details.title">
      <h2>{{details.title}}</h2>
      <span>{{details.author}}i</span>
      <span>{{details.year}}</span>
  </div>
</template>

<script>
export default {
  name: 'Dischi',
  props: {
      details: Object,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    .disc{
        width: 18%;
        text-align: center;
        background-color: rgb(46, 58, 70);
        padding-bottom: 3%;
        margin-bottom: 20px;
        img{
            width: 150px;
            height: 150px;
            margin-top: 15px;
        }
        h2{
            font-size: 20px;
            color: white;
            margin: 10px 45px;
        }
        span{
            display: block;
            color: rgb(143, 142, 142);
        }
    }
</style>
