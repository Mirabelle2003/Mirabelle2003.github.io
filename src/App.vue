<template>
  <div id="app">
    <header>
      <h1>VUE JS</h1>
      <nav>
        <router-link to="/home">Accueil</router-link>
        <router-link to="/about">À propos</router-link>
      </nav>
    </header>
    
    <router-view></router-view>
  </div>
</template>

<style>
header {
  background-color: #370d0d;
  color: white;
  padding: 7px;
  text-align: center;
  justify-content: space-between; 
}

nav {
  margin-top: 10px;
}

nav a {
  color: white;
  margin-right: 100px;
  margin-left: 100px;
  text-decoration: none;
}

.nav-container {
  display: flex;
 
  margin-top: 10px;
}

.nav-link {
  color: white;
  text-decoration: none;
}

</style>
