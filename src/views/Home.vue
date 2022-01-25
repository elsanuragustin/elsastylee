<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  },

  mounted(){
    this.getData()
  },
  
  methods:{
    async getData(){
      let {data,salah}= await this.$supabase
      .from('tb_produk')
      .select()

      if(data) console.log(data)
      if(salah) console.error(salah)
    },
  },
};
</script>
