<template>
    <header>
  <div class="navbar container">  
    <!-- Logo -->
    <div class="brand">
          <img src="@/assets/img/dc-logo.png">
    </div>
    <!-- /Logo -->

    <!-- Menù -->
    <div class="menu">
      <ul class=items>
        <li v-for="(link,index) in links" :key="index" :class="(link == currentLink) ? 'active' : null"  @click="currentLink(index)">
           <a> {{link.text.toUpperCase()}} </a>
        </li>
      </ul>
    </div>
    <!-- /Menu -->


  </div>
  </header>
  
</template>

<script>
import links from "@/assets/data/Links.js"
export default {
  name: 'Header',
  data() {
    return {
      links: links,
      currLink: '',
    }
  },
  methods: {
    currentLink(index){
      this.currLink = this.links[index];
    }
  },
  mounted(){
    this.currLink = this.links[1];
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "./style/general";
.brand {
    width: 4.375em;
    padding: 1.25em 0em;

    img {
      width: 100%;
    }

  }

.navbar {
  height: 6.25em; 
  display:flex; 
  justify-content: space-between;  
  align-items: center; 
}

nav {
  display: flex;
  justify-content: space-between;
}

ul {
  list-style: none;
  display: flex;
  justify-content: space-between;
  line-height: 6rem;

    li  {
        padding: 0px 0.625em;

    &:hover {
      color:$blue-hover-link;
    }
        }
    }

</style>
