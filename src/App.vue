<template>
  <div id="app">
    <Navbar></Navbar>
    <div id="contents">
      <Sidebar></Sidebar>
      <Release></Release>
    </div>
    </div>
</template>

<style>
#app {
  width: 100%;
  height: 100%;
}

#contents:after {
  content: '';
  display: block;
  clear: both;
}
</style>


<script>
import Navbar from './components/Navbar';
import Sidebar from './components/Sidebar';
import Release from './components/Release';

export default {
  name: 'App',
  components: {
    Navbar,
    Sidebar,
    Release
  }
};
</script>
