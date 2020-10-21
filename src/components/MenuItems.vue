<template>
   <ul class="menu-group">
        <li class="menu-item">
          <router-link to="/">HELLO WORLD</router-link>
        </li>
        <li class="menu-item">
          <router-link to="/todo">TODO LIST</router-link>
        </li>
   </ul> 
</template>

<script>
export default {
  name: "MenuItems",
}
</script>
<style scoped>
  .menu-group {
    padding: 0;
  }
  .menu-item {
    height: 40px;
    width: 100%;
    margin-top: 4px;
    list-style-type: none;
    text-align: left;
    font-size: 1em;
    font-weight: bold;
    color: black;
    padding-left: 0.5rem;
    padding-top: 10px;
    box-sizing: border-box;
  }
  .menu-item a:active {
    color: greenyellow;
  }
  .menu-item:hover {
    background-color: gray;
  }
</style>