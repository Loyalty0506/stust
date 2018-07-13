<template>
  <div>
    <input v-model="text"/>
    <ul>
      <li v-for="(item, idx) in list" :key="idx">
        {{item}}
      </li>
    </ul>
  </div>
</template>

<script>
import countryNames from './countryNames.json';

export default {
  data(){
    return {
      text: '',
    };
  },
  computed:{
    list(){
      return countryNames.filter(name =>{
        return name.toLowerCase().includes(this.text.toLowerCase())
      });
    },
  },
};
</script>