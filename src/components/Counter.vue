<template>
  
  <h2>{{ customTitle }}</h2>
  <p>{{counter}} <sup>2</sup> = {{ squareCounter }}</p>
  <button @click="increase"> +1 </button>
  <button @click="decrease"> -1 </button>
</template>

<script>
export default {
  name: 'Counter',
  props:{
    title: String,
    start: {
      type: Number,
      default: 2,
      // required: true,
      validator(value){
        return value >= 0
      }
    },
  },

  data(){
    return {
      counter: +this.start
    }
  },

  methods: {
    increase(){
      this.counter++
    },
    decrease(){
      this.counter--
    }
  },

  computed: {
    squareCounter() {
      return this.counter * this.counter
    },
    customTitle(){
      return this.title || ' Counter'
    }
  }
}

</script>

<style>
button{
  margin: 0 5px;
  background-color: steelblue;
  color: #fff;
  border-radius: 5px;
  padding: 5px 15px;
  cursor: pointer;
}
</style>
