<template>
      <div>
          <h1>Life cycle Hooks Component</h1>
          <button @click="hookData++">Increment</button>
          {{hookData}}   <!--{{increment}} -->
          
          <button v-on:click="text=!text">
            <span v-if="text" >Hide</span>
            <span v-else >Show</span>
          </button>
          {{text}}
      </div>
</template>

<script>
export default {
       name:'LifeCycleMethods',
       props:['hookData','text'],
       data(){
            return{
              increment:0,
            }
       },
      //  methods:{
      //        incremented(){
      //          return this.hookData++
      //        }
      //  },
       beforeDestroy(){
        alert('beforeDestroy Hook has been called')
        console.log('beforeDestroy Hook has been called');
       },
       destroyed(){
         alert('Destroyed Hook has been called')
         console.log('Destroyed Hook has been called');
       }
}
</script>

<style>

</style>