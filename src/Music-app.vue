<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <!-- <HelloWorld msg="Hello Vue 3.0 + Vite" counter="1" /> -->
  <!-- <NewScreen msg="Welcome to new screen"/> -->
  <WatcherExample msg="Welcome to Watcher"/>
</template>

<!-- ??? -->
<script>
import HelloWorld from './components/HelloWorld.vue'
import NewScreen from './components/NewScreen.vue'
import WatcherExample from './components/WatcherExample.vue'

export default {
  name: 'MusicApp',
  components: {
    HelloWorld,
    NewScreen,
    WatcherExample,
  }
}
</script>
