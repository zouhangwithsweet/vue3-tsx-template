<template>
  <img src="./logo.png">
  <h1>Hello Vue 3!</h1>
  <Wrapper>
    <Input :value="count"/>
  </Wrapper>
  <button @click="inc">Clicked {{ count }} times.</button>
</template>

<script>
import { ref } from 'vue'
import Input from './Input.vue'
import Wrapper from './components/wrapper.vue'
export default {
  setup() {
    const count = ref(0)
    const inc = () => {
      count.value++
    }
    const changeHandler = (value) => {
      console.log(value)
    }
    return {
      count,
      inc,
      changeHandler,
    }
  },
  components: {
    Input,
    Wrapper,
  }
}
</script>

<style scoped>
img {
  width: 200px;
}
h1 {
  font-family: Arial, Helvetica, sans-serif;
}
</style>
