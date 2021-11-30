<template>
  <header>
      <div class="greybox">
        <i class="fab fa-spotify"></i>

        <select name="" id="selector" v-model="key" @change="$emit('changeGenre', key)" >
          <option :value="'all'">Seleziona Genere</option>
          <option :value="'Rock'">Rock</option>
          <option :value="'Pop'">Pop</option>
          <option :value="'Jazz'">Jazz</option>
          <option :value="'Metal'">Metal</option>
      </select>

      </div>

      

  </header>
</template>

<script>
export default {
  name: 'MyHeader',
    data(){
          return {
              key: "all"
          }
      }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    .greybox{
        background-color: rgb(46, 58, 70);
        display: flex;
        justify-content: space-between;
        #selector{
          margin: 10px;
          width: 10%;
        }
        .fa-spotify{
            font-size: 50px;
            color: rgb(24, 245, 24);
            margin: 10px;
        
        }
    }
</style>
