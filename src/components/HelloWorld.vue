<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>How I Built This Page</h2>
    <p>
      To install Vue CLI, I ran the command
      <code>npm install -g @vue/cli</code>. Then, I created a new project using
      <code>vue create my-vue-project</code>.
    </p>

    <h2>Building the Page</h2>
    <p>
      I modified the <code>HelloWorld.vue</code> component to include this
      content. I used Vue's templating syntax to structure the HTML and added
      some basic CSS for styling.
    </p>

    <h2>Difficulties Encountered</h2>
    <p>
      One difficulty I encountered was configuring the project to work with
      GitHub Pages. Initially, I faced issues with the deployment process and
      ensuring that the changes were reflected on the GitHub Pages site.
    </p>
    <p>
      To deploy to GitHub Pages, I followed these steps:
      <ol>
        <li>First, I installed the <code>gh-pages</code> package by running <code>npm install gh-pages --save-dev</code>.</li>
        <li>Then, I added the following scripts to my <code>package.json</code> file:
          <pre><code>
"scripts": {
  "deploy": "vue-cli-service build && gh-pages -d dist"
}
          </code></pre>
        </li>
        <li>Next, I configured the <code>vue.config.js</code> file to set the correct public path:
          <pre><code>
module.exports = {
  publicPath: process.env.NODE_ENV === 'production'
    ? '/my-vue-project/'
    : '/'
}
          </code></pre>
        </li>
        <li>Finally, I ran the deployment script using <code>npm run deploy</code>.</li>
      </ol>
      Following these steps ensured that my changes were successfully deployed and visible on GitHub Pages.
    </p>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
};
</script>

<style scoped>
.hello {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
