<template>
  <div id="nav-org" >
    <nav class="navbar-container" >
      <ul>
        <li> <router-link to="/home-org" class="navbar-item">REQUESTS</router-link> </li>
        <li> <router-link to="/arenas-org" class="navbar-item">ARENAS</router-link> </li>
        <li> <router-link to="/profile" class="navbar-item">PROFILE</router-link> </li>
        <li> <button class="logout_btn" @click="showModal = true">LOG OUT</button> </li>
        <li style="float:right" id="logo"> <img src="../assets/nav_logo.png" width="auto" height="30" /> </li>
      </ul>
    </nav>

    <transition name="fade" appear>
      <div class="modal-overlay" v-if="showModal" @click="showModal = false" > </div>
    </transition>

    <transition name="slide" appear>
      <div class="modal" v-if="showModal">
        <h1>Are you sure you want to log out?</h1>
        <hr style="height:10pt; visibility:hidden;" />
        <router-link to="/">
          <button class="button" @click="showModal = false"> Yes </button>
        </router-link>
        <button class="button" @click="showModal = false"> No </button>
      </div>
    </transition>

  </div>
</template>

<script>
export default {
  name: "nav-org",
  data() {
    return {
      showModal: false
    };
  }
};
</script>

<style scoped>

.navbar-container {
  left          : 0;          
  top           : 0;            
  width         : 100%;      
  filter        : drop-shadow(0px 3px 3px rgba(0, 0, 0, 0.1));
  margin-bottom : 20px;
}

ul {
  list-style-type : none;
  margin          : 0;
  padding         : 0;
  overflow        : hidden;
  background-color: white; 
  border-radius   : 4px; 
}

li { float: left; }

li a {
  display         : block;
  font-family     : Bebas Neue, sans-serif;
  font-size       : 24px;
  color           : #979797;
  text-align      : center;
  padding         : 16px 16px;
  text-decoration : none;
  margin-bottom   : 0px;
}

li a:hover { color: #2c2c2c; }

a.router-link-exact-active { color: #ed4144 !important; }

#logo {
  display         : block;
  font-family     : Roboto, sans-serif;
  font-size       : 20px;
  font-weight     : bold;
  color           : #ed4144;
  text-align      : center;
  padding         : 14px 16px;
  text-decoration : none;
}

.logout_btn {
  float               : left;
  display             : block;
  font-family         : Bebas Neue, sans-serif;
  font-size           : 24px;
  color               : #979797;
  text-align          : center;
  padding             : 16px 16px;
  text-decoration     : none;
  margin-bottom       : 14px;
  background-color    : white;
  border              : none;
  width               : auto;
  margin              : 0px 0px;
  cursor              : pointer;
  transition-duration : none;
  border-radius       : 0;
}

.logout_btn:hover {
  color   : #2c2c2c;
  filter  : none;
}

.logout_btn:focus { outline: none; }

</style>
