<template>
<div>
    <div v-if="discList.length === 0" class="load">
        Loading...
    </div>
    <div v-else id="ContainerDisc">
      <Disco v-for="list, i in filteredGen" :key="i" :details="list" />
  </div>
</div>
</template>

<script>
import axios from 'axios'
import Disco from '@/components/Disco.vue'

export default {
  name: 'Dischi',
  components: {
    Disco,
  },
  props: {
      selectedGenre: String
  },
  data() {
      return {
          apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
          discList: [],
          searchGen: "",
      }
  },
  created(){
      this.getDisc();
  },
  computed: {
      filteredGen(){
          if(this.selectedGenre === 'all'){
              return this.discList
          }

          return this.discList.filter((item) => {
              return item.genre.includes(this.selectedGenre)
          })
      }
  },
  methods: {
      getDisc(){
          axios
          .get(this.apiUrl)
          .then((result) =>{
              this.discList = result.data.response
            // console.log(result);
          });

      },

      getGen(genType) {
          this.searchGen = genType
      }
      

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    #ContainerDisc{
        width: 60%;
        margin: 20px auto;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-evenly;
    }
    .load{
        color: white;
        text-align: center;
    }
    .filter{
        display: flex;
        justify-content: center;
        align-items: center;
        height: 50px;
    }
</style>
