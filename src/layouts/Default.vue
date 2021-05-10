<template>
  <div class="layout">
    <header class="header">
      <strong>
        <g-link to="/" class="handwriting site-title">{{
          $static.metadata.siteName
        }}</g-link>
      </strong>
      <nav class="nav">
        <g-link class="nav__link nav--yellow" to="/">Home</g-link>
        <g-link class="nav__link nav--red" to="/events">Events</g-link>
      </nav>
    </header>
    <transition name="fade" appear>
      <main>
        <slot />
      </main>
    </transition>
    <footer>
      Built with
      <a
        href="https://gridsome.org/docs"
        target="_blank"
        rel="noopener"
        class="link--gridsome"
        >Gridsome</a
      >
      by
      <a
        href="https://twitter.com/TerabyteTiger"
        target="_blank"
        rel="noopener"
        class="link--blue"
        >Tyler</a
      >
    </footer>
  </div>
</template>

<static-query>
query {
  metadata {
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

/* Transition */
.fade-enter-active {
  transition: opacity 0.5s;
}

.fade-enter {
  opacity: 0;
}

/* CSS */
body > div {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

body {
  font-family: "Open Sans", sans-serif;
  margin: 0;
  padding: 0;
  line-height: 1.5;
  font-size: 1.1rem;
}

.layout {
  max-width: 760px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
  min-height: 100vh;
}

main {
  flex-grow: 1;
}

footer {
  text-align: center;
  width: 100%;
  max-width: inherit;
  padding: 20px 0;
}

.nav__link {
  margin-left: 20px;
  padding: 10px 15px;
  font-weight: bold;
}

.handwriting {
  font-family: "Patrick Hand", cursive;
}

.flex-row {
  display: flex;
  align-items: center;
}

.space-between {
  justify-content: space-between;
}

.site-title {
  padding: 5px 15px;
  text-decoration: none;
  background-color: hsl(197, 100%, 55%);
  color: black;
  border: 4px solid hsl(197, 100%, 55%);
  font-size: 1.5rem;
  margin: 8px 0;
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

.header * {
  /* Prevent Margin Collapse */
  display: inline-block;
}

.header {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 8px;
}

.header > nav > a:first-child {
  margin-left: 0;
}

@media only screen and (min-width: 500px) {
  /* Larger Screens Only */
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
    height: 80px;
    flex-direction: row;
  }
}

.link--red {
  border-bottom: 3px solid hsl(345, 70%, 50%);
  text-decoration: none;
}

.link--blue {
  border-bottom: 3px solid hsl(197, 100%, 55%);
  text-decoration: none;
}

.link--yellow {
  border-bottom: 3px solid hsl(43, 100%, 49%);
  text-decoration: none;
}

.link--gridsome {
  border-bottom: 3px solid hsl(157, 55%, 58%);
  text-decoration: none;
}
</style>
