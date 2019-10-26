<template>
<div class="b-container">
<div class="b-row">
    <div class="b-col-4">
     <SideNav/>
    </div>
    <div class="b-col-8">
        <Header/>
    </div>
  
</div>
<div class="b-container">

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
