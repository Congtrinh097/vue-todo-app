<template>
  <div id="app">
    <div class="left-menu">
      <h1>TODO APP</h1>
      <MenuItems></MenuItems>
    </div >
    <div class="content">
       <router-view/>
    </div>
  </div>
</template>

<script>
import MenuItems from '@/components/MenuItems';
export default {
  name: 'App',
  components: { MenuItems }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100vw;
  height: 100vh;
  display: flex;
}
.left-menu {
  width: 20vw;
}
.content {
  background: honeydew;
  width: 80vw;
}
</style>
