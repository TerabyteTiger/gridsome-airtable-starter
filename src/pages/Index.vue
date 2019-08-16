<template>
  <Layout>
    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <g-image 
      alt="Yellow background with grey pencils. Photo by Joanna Kosinska on Unsplash" 
      src="~/assets/mainImage.jpg" 
      width="400" 
      class="headerImage"
    />
    <section>
      <h1 class="handwriting">Welcome to Local Fake Events!</h1>
      <p>
        We're glad you're here and interested in learning more about our offerings in the community! 
        <br/>
        <br/>
        You can check out the full list of available events on our <g-link class="link--red" to="/events">Events</g-link> page!
      </p>
    </section>

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
.headerImage {
  border: 4px solid hsl(43, 100%, 49%);
  border-radius: 15px;
  margin: 0 auto;
  display: block;
  padding: 4px;
  max-width: 100%;
}

section > h1 {
  font-size: 2.6rem;
}
</style>
