<template>
  <div>
    <TheHeader @genre-clicked="getValue" :genre-array="genreArray"/>
    <TheMain :genre-selected="genreSelected" @genre-array="getGenreArray"/>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue'
import TheMain from './components/TheMain.vue'

export default {
  name: 'App',
  data(){
    return{
      genreSelected: '',
      genreArray: [],
    }
  },
  components: {
    TheHeader,
    TheMain,
  },
  methods:{
        getValue(value){
          console.log(2, value)
          this.genreSelected = value
        },
        getGenreArray(array){
          this.genreArray= array
        }
    }
}
</script>

<style lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body{
  height: 100vh;
  font-family: sans-serif;
}
</style>
