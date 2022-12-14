<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to="/products">Products</router-link> |
    <router-link to="/admin">Admin</router-link> |
    <router-link to="/contact">Contact</router-link> 
  </nav>
  <navbar/>
  <router-view/>
  <Footer/>
</template>

<script>
import navbar from './components/NavBar.vue'
import Footer from './components/Footer.vue'
export default {
  components: {
    navbar, 
    Footer
  },
  data(){
        return {
            products: JSON.parse(localStorage.getItem('products')) ?
            JSON.parse(localStorage.getItem('products')) :[
                {
                    id: 1,
                    productName: 'Konke',
                    price: 0
                },
                {
                    id: 2,
                    productName: 'Tiger',
                    price: 52
                },
                {
                    id: 3,
                    productName: 'Stuart',
                    price: 12
                }
            ]
        }
    }
}

</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}


nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
