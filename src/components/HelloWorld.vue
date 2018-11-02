<template>
  <div>
    <h1>这是父组件的信息</h1>
   <child v-on:ctest="showChildMsg()"></child>
  </div>
</template>

<script>
import child from './test';
export default {
  data () {
    return {

    }
  },

  components: {
    child
  },

  props: [],

  watch: {},

  computed: {},

  mounted () {},

  methods: {
    showChildMsg(){
      console.log(data);
    }
  }
}

</script>
<style  scoped>
</style>