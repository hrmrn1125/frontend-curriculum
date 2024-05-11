<template>
  <div id="app">
    <router-view/>
  </div>
</template>

export default {
  name: 'app'
}

<style>
#app {
  background: #B8C2C9;
  color: #2c3e50;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}

body {
  cursor: pointer;
  margin: 0;
  padding: 0;
  width: 100vw;
  height: 100vh;
}

ul {
  margin: 0;
  padding: 0;
}

li {
  list-style: none;
}

h1 {
  margin: 0 auto 12px 0;
  padding: 0;
  text-align: left;
  font-size: 28px;
  font-weight: 900;
}

h2 {
  margin: 0 14px 24px;
  padding: 0 0 6px 4px;
  text-align: left;
  border-bottom: 1.4px solid #D1D1D1;
  font-size: 20px;
  font-weight: 900;
}

p {
  margin: 0;
  padding: 0;
}

a {
  font-size: 16px;
  font-weight: 600;
  text-decoration: none;
  color: #333333;
}

span {
  font-size: 16px;
  font-weight: 600;
  text-decoration: none;
  color: #333333;
}

table{
  width: calc(100% - 38px);
  border-collapse: collapse;
}

th {
  text-align: center;
  background-color: #406D9F;
  color: #FFFFFF;
}

td {
  background-color: #DBE4EF;
}

th,td{
  border: 1px #FFFFFF solid;
  padding: 8px 10px;
}

.desktop-only {
  display: block;
}

.smartphone-only {
  display: none;
}

.p-displayNone {
  display: none;
  height: 0;
  width: 0;
  opacity: 0; 
}

@media screen and (max-width:767px) {
  .desktop-only {
    display: none;
  }

  .smartphone-only {
    display: block;
  }
}
</style>
