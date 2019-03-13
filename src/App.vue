<template>
    <div class="container">      
    <quotegrid :quotes="quotes"></quotegrid>
    </div>
</template>

<script>
import Quotegrid from './components/Quotegrid.vue';
    export default {
        data(){
          return{
            quotes: ['First quote']
          }            
        },
        components:{
            Quotegrid,
        }
        
    }
</script>

<style>
</style>
