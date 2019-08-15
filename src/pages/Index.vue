<template>
  <Layout>
    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <g-image 
      alt="Yellow background with grey pencils. Photo by Joanna Kosinska on Unsplash" 
      src="~/assets/mainImage.jpg" 
      width="500" 
      class="headerImage"
    />
    
    <h1 class="handwriting">Welcome to Local Fake Events!</h1>
    <p>
      We're glad you're here and interested in learning more about our offerings in the community! 
      <br/>
      <br/>
      You can check out the full list of available events on our <g-link class="link--red" to="/events">Events</g-link> page!
    </p>

    <p class="home-links">
      Built with <a href="https://gridsome.org/docs" target="_blank" rel="noopener" class="link--gridsome">Gridsome</a> by <a href="https://twitter.com/PichuPlayer" target="_blank" rel="noopener" class="link--blue">Tyler</a>
    </p>

  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: 'Hello, world!'
  }
}
</script>

<style>

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

.headerImage {
  border: 4px solid hsl(43, 100%, 49%);
  border-radius: 15px;
  margin: 0 auto;
  display: block;
  padding: 4px;
  max-width: 100%;
}
</style>
