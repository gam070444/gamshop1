<template>
  <div id="app">
    <div>
      <b-navbar toggleable="lg" type="light" variant="light">
        <router-link to="/">
        </router-link>
        <b-navbar-brand href="#">GAM BAKERY HOUSE</b-navbar-brand>

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <router-link class="col-5" style="color: brown" to="/"
              >Home</router-link
            >
            <router-link class="col-5" style="color: brown" to="/about"
              >Order</router-link
            >
          </b-navbar-nav>

          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <b-nav-form> </b-nav-form>
            <router-link to="/about" class="col-7">
            <b-button  squared variant="primary" @click="submit()">
              ยืนยัน
            </b-button></router-link>
            <b-button  squared variant="danger" @click="cleardata()">
              ยกเลิก
            </b-button>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </div>
    <router-view @Order="Sorder" :data="data" :Total="Total"/>
    
  </div>
</template>
<script>
export default {
  data() {
    return {
      s: [],
      data:[],
      Total:0
    };
  },
   methods:{
    Sorder(v){
      this.s.push(v);
      this.$emit("Order",this.s);
    },
    submit(){
      this.data=this.s;
      this.Total=0;
      for(var i=0;i<this.data.length;i++){
        this.Total = this.Total+this.data[i].Total;
      
      }
    },
    cleardata(){
      this.data=[];
      this.Total=0;
    }
  },
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #856868;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #000000;
}

#nav a.router-link-exact-active {
  color: rgb(83, 30, 30);
}
</style>
