<template>

  <div>
    
    <!-- layout -->
    <NavBar></NavBar>
    
    <router-view></router-view>

  </div>
  
</template>


<script>

  import NavBar from './components/NavBar.vue'
  import BusEvent from './components/BusEvent.vue';

  
  export default {
    name: 'app',
    components: { 
      'NavBar': NavBar,
    },
    data () {
      return {
        locale: "ru",
        pathData: document.location.href.indexOf("8080") != -1 ? document.location.href.split(":").slice(0,2).join(":")+":8081" : document.location.href.split("/").slice(0,3).join("/"),
      }
    }, 

    mounted() {
      console.log(this.$store)
      // this.aviaLoadCities()

      // this.getIP();
      // this.getVT();
      this.$store.state.pathData = this.pathData;
    },

    methods: {

      // aviaLoadCities() {
      //   let self = this;

      //   this.$http.get('http://127.0.0.1:8081/aviaGetCities')
      //   .then(response => {
      //     if(response.status == 200){
      //       // console.log(response.data)
      //       BusEvent.$emit('aviaLoadCities', response.data);
      //     }else{
      //       console.log("Server error: "+ response.status);
      //     }
      //   });
      // },

    },

    watch:{
      $route (to, from){

        // if(to.fullPath === "/"){

        //   $(".navbar .nav-item .nav-link").css({
        //     "color": "#D6D6D6",
        //     "font-weight": "700"
        //   })
        //   $(".navbar .nav-item.active .nav-link").css({
        //     "color": "white",
        //   })
        //   $(".navbar .nav-item .nav-link:hover").css({
        //     "color": "white",
        //   })

        // }else{

        //   $(".navbar .nav-item .nav-link").css({
        //     "color": "#707070",
        //     "font-weight": "700"
        //   })
        //   $(".navbar .nav-item.active .nav-link").css({
        //     "color": "#F09A24",
        //   })
        //   $(".navbar .nav-item .nav-link:hover").css({
        //     "color": "#F09A24",
        //   })

        // }
      }
    }, 
  }

</script>

<style>
  
  .spaceDiv{
    height: 550px;
  }
</style>
