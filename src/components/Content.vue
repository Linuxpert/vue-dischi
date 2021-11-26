<template>
<div>
    <div v-if="discList.length === 0" class="load">
        Loading...
    </div>
    <div v-else id="ContainerDisc">
      <Dischi v-for="list, i in discList" :key="i" :details="list" />
  </div>
</div>
</template>

<script>
import axios from 'axios'
import Dischi from '@/components/Dischi.vue'

export default {
  name: 'Content',
  components: {
    Dischi
  },
  data() {
      return {
          apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
          discList: [],
      }
  },
  created(){
      this.getDisc();
  },
  methods: {
      getDisc(){
          axios
          .get(this.apiUrl)
          .then((result) =>{
              this.discList = result.data.response
            // console.log(result);
          })
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
</style>
