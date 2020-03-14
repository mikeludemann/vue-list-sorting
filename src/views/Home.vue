<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <ListSorting id="mainList" cid="sorting" :dataList='[{ id: 1, name: "John Doe" },{ id: 2, name: "Mary Watson" },{ id: 3, name: "Dave Beck" },{ id: 4, name: "Brooke Tyson" }]'></ListSorting>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';
import ListSorting from '@/components/list-sorting.vue';

export default {
  name: 'Home',
  components: {
    HelloWorld,
    ListSorting
  }
}
</script>
