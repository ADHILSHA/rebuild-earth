<template>
<div >
<div class="navContainer flex md:flex-row-reverse flex-wrap">
    <div class="w-full  md:w-4/5   text-center text-gray-200 header">
        <Header/>
        <div class=" mainContent">
               <div class="card">

               </div>
           
        </div>
    </div>
    <div class=" w-full md:w-1/5 bg-gray-400 text-center text-gray-700 sideNav">
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
.mainContent{
    background-color:rgb(247, 247, 247);;
    width:100%;
    height:577px;
}
.card{
     background-color:#ffffff;
    width:500px;
    height:300px;
    position: relative;
    top: 150px;
    margin:auto;
    border: 1px solid #D1CFCF;
box-sizing: border-box;

}
</style>
