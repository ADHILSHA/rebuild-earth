<template>
<div >
<div class="navContainer flex md:flex-row-reverse flex-wrap">
    <div class="w-full md:w-3/4 bg-gray-500 p-4 text-center text-gray-200 header">
        <Header/>
    </div>
    <div class=" w-full md:w-1/4 bg-gray-400 p-4 text-center text-gray-700 sideNav">
     <SideNav/>
    </div>
    
  


</div>
</div>
  
</template>

<script>
import Header from './Header'
import SideNav from './SideNav'
export default {
  mounted(){
    this.getData()
  },
  name: 'Home',
  data () {
    return {
      
    }
  },
  components:{
      Header,
      SideNav
  },
  methods:{
    getData(){
        let config = {
                    headers: {
                        'x-CSRFToken': '',
                        }
                      }
      axios.get('https://api.rebuildearth.org/api/camps/?limit=10&offset=1',config)
              .then(response =>{
              })
              .catch(( {response} ) => {            
                console.log(response);
              });
    }
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
