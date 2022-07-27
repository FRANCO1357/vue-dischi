<template>
  <div>
    <TheHeader @genre-clicked="getValue"/>
    <TheMain :genre-selected="genreSelected"/>
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
