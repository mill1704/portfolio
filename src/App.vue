<template>
  <div id="app">
    <div id="nav">
      <navbar />
    </div>
    <div id="content">
      <router-view />
    </div>
  </div>
</template>

<script>
import './assets/style/design.scss'
import navbar from './components/navbar';

export default {
  components:{
    navbar
  }
}
</script>

