<template>
  <div class="container">
    <div>
      <p>hello</p>
      <form>
        <p>Enter your Name</p>
        <input type="text" v-model="name" />
        <p>Enter your links</p>
        
      </form>
    </div>
    <div>
      <p>Right Side</p>
      <p>{{name}}</p>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';
export default {
  setup(){
    const name = ref('')


    return {
      name
    }
  }
};
</script>

<style>
.container {
  width: 90%;
  margin: auto;
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
}
</style>
