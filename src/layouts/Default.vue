<template>
  <div class="layout">
    <header class="header">
      <strong>
        <g-link to="/" class="handwriting site-title">{{ $static.metaData.siteName }}</g-link>
      </strong>
      <nav class="nav">
        <g-link class="nav__link nav--yellow" to="/">Home</g-link>
        <g-link class="nav__link nav--red" to="/events">Events</g-link>
      </nav>
    </header>
    <slot/>
  </div>
</template>

<static-query>
query {
  metaData {
    siteName
  }
}
</static-query>

<style>
/* 
"hsl(43, 100%, 49%)", Airtable Yellow
"hsl(197, 100%, 55%)", Airtable Blue
"hsl(345, 70%, 50%)"  Airtable Red 
*/
body {
  font-family: 'Open Sans', sans-serif;
  margin:0;
  padding:0;
  line-height: 1.5;
  font-size: 1.1rem;
}

.layout {
  max-width: 760px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  height: 80px;
}

.nav__link {
  margin-left: 20px;
  padding: 10px 15px;
  font-weight: bold;
}

.handwriting {
  font-family: 'Patrick Hand', cursive;
}

.flex-row {
  display: flex;
  align-items: center;
}

.space-between {
  justify-content: space-between
}

.site-title {
  padding: 5px 15px;
  text-decoration: none;
  background-color: hsl(197, 100%, 55%);
  color: black;
  border: 4px solid hsl(197, 100%, 55%);
  font-size: 1.5rem;
  
}

.nav--blue {
  border: 4px solid hsl(197, 100%, 55%);
  color: black;
  border-radius: 10px;
}

.nav--blue:hover {
  background-color: hsl(197, 100%, 90%);
}

.nav--red {
  border: 4px solid hsl(345, 70%, 50%);
  color: #000000;
  border-radius: 10px;
}

.nav--red:hover {
  background-color: hsl(345, 100%, 90%);
}

.nav--yellow {
  border: 4px solid hsl(43, 100%, 49%);
  color: #000000;
  border-radius: 10px;
}

.nav--yellow:hover {
  background-color: hsl(43, 100%, 90%);
}

</style>
