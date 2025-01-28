<template lang="html">
    <div>
        <h3> componente de personagens </h3>
    </div>
</template>

<script>
import { publicKey, secretKey } from '@/marvel';
import axios from 'axios';
export default {
    name: 'Characters',

    mounted(){
        this.getCharacters();
    },

    methods:{
    getCharacters: function(){

      axios.get(`http://gateway.marvel.com/v1/public/characters?apikey=${publicKey}`)
        .then((result) => {
            console.log(result);
        }) 
        .catch((error) => {
            console.log(error);
        });
    }
  }
}
</script>

<style lang="css">
</style>
