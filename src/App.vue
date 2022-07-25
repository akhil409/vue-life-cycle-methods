<template>
  <div id="app">
        <div v-if="display">
            <LifeCycleMethods v-bind:hookData="hookData" v-bind:text="text"/>
        </div> <br>
        <button v-on:click="deleteComponent">
            <span v-if="display">Destroy Component</span>
            <span v-else>Restore Component</span>
        </button>
  </div>  
</template>

<script>
import LifeCycleMethods from './components/LifeCycleMethods.vue'

export default {
  name: 'App',
  components: {
    LifeCycleMethods,
},
    data(){
      return{
           hookData:1,
           text:"Welcome to Life Cycle Hooks Page",
           display:true,
           data:[],
      }
    },
    methods:{
        deleteComponent(){
            this.display=!this.display
        }
    },
    beforeCreate(){
       alert('beforeCreate Hook has been called')
       console.log('beforeCreate Hook has been called');
    },
    created(){
         alert('Created Hook has been called')
         console.log('Created Hook has been called',this.hookData,this.text);
        //  axios.get('https://jsonplaceholder.typicode.com/posts').then( res => this.data = res)
    },
    beforeMount(){
         alert('beforeMount Hook has been called')
         console.log('beforeMount Hook has been called');
    },
    mounted(){
         alert('Mounted Hook has been called')
        console.log('Mounted Hook has been called',this.hookData,this.text);
        this.$data.text='Pleasure is Mine....!';

    },
    beforeUpdate(){
         alert('beforeUpdate Hook has been called')
        console.log('beforeUpdate Hook has been called');
    },
    updated(){
         alert('Updated Hook has been called')
        console.log('Updated Hook has been called',this.hookData,this.text);
    },
    // beforeDestroy(){
    //     alert('beforeDestroy Hook has been called')
    //     console.log('beforeDestroy Hook has been called');
    //     // this.hookData=null
    //     // delete this.hookData
    // },
    // destroyed(){
    //      alert('Destroyed Hook has been called');
    //      console.log('Destroyed Hook has been called');
    //     //  this.$destroy();0
    //     //  console.log(this)
    // }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
