<template>
  <header>
      <div class="greybox">
        <i class="fab fa-spotify"></i>
      </div>
  </header>
</template>

<script>
export default {
  name: 'MyHeader',
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    .greybox{
        background-color: rgb(46, 58, 70);
        .fa-spotify{
            font-size: 50px;
            color: rgb(24, 245, 24);
            margin: 10px;
        
        }
    }
</style>
