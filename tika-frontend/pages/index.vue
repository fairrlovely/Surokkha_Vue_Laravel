<template>
  <div>
    <button @click.prevent="testBackendRequest">Request API</button>
    <h1 v-if="apiValue" class="font-bold text-3xl">Check: {{apiValue}}</h1>
    <Tutorial/>
  </div>
</template>

<script>
export default {
  data(){
    return {
      apiValue:''
    }

  },
  mounted(){
    this.testBackendRequest();
  },
  methods:{
    testBackendRequest(){
      this.$axios.get('/test').then(res=>{
          this.apiValue=res.data;
    });
    }
  }
}
</script>
