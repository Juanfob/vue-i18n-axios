<template>
  <div id="app"> 

   <div class="locale-changer">
    <select v-model="$i18n.locale">
      <option v-for="(lang, i) in langs" :key="`Lang${i}`" :value="lang">{{ lang }}</option>
    </select>
  </div>

    {{ $t('lang.notice.msg')}}  

    <Users></Users>
    <Posts></Posts>
    <photos></photos>
  </div>
</template>

<script>

import Users from './components/Users.vue'
import Posts from './components/Posts.vue'
import Photos from './components/Photos.vue'

export default {
  name: 'App',
  data(){
    return {
     langs: ['es', 'en', 'jp'] 
    }
  },

  components: {
    Users,
    Posts,
    Photos,
  
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
