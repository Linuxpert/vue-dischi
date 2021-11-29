<template>
  <div id="filtro">
    <h2>
        Filtra i generi:
    </h2>
    <select name="" id="" v-model="key" @change="$emit('changeGenre', key)" >
        <option :value="'all'">All</option>
        <option :value="'Rock'">Rock</option>
        <option :value="'Pop'">Pop</option>
        <option :value="'Jazz'">Jazz</option>
        <option :value="'Metal'">Metal</option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'Filtro',
    data(){
        return {
            key: "all"
        }
    }
}
</script>

<style scoped lang="scss">

    #filtro{
        display: flex;
        h2{
            color: #fff;
            margin-right: 10px;
        }
    }

    
</style>
