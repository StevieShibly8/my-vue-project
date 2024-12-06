<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    
    <h2>How I Installed the Framework</h2>
    <p>
      To install Vue CLI, I ran the command
      <code>npm install -g @vue/cli</code>. This globally installs the Vue CLI tool, which is necessary for creating and managing Vue projects. 
      Then, I created a new project using the command
      <code>vue create my-vue-project</code>. This command initializes a new Vue project with a default configuration, setting up the necessary files and directories.
    </p>

    <h2>Building the Page</h2>
    <p>
      I modified the <code>HelloWorld.vue</code> component to include this content. I used Vue's templating syntax to structure the HTML and added some basic CSS for styling.
      Specifically, I added several sections to the template, including headings and paragraphs to describe the process of building the page. 
      I also used Vue's data binding feature to dynamically display the message stored in the <code>msg</code> property.
    </p>

    <h2>Difficulties Encountered</h2>
    <p>
      One difficulty I encountered was configuring the project to work with GitHub Pages. Initially, I faced issues with the deployment process and ensuring that the changes were reflected on the GitHub Pages site.
      The main challenge was setting the correct public path and ensuring that the build output was correctly deployed to the <code>gh-pages</code> branch.
    </p>
    <p>
      To deploy to GitHub Pages, I followed these steps:
      <ol>
        <li>First, I installed the <code>gh-pages</code> package by running <code>npm install gh-pages --save-dev</code>. This package helps to deploy the build output to the <code>gh-pages</code> branch.</li>
        <li>Then, I added the following scripts to my <code>package.json</code> file to automate the deployment process:
          <pre><code>
"scripts": {
  "deploy": "vue-cli-service build && gh-pages -d dist"
}
          </code></pre>
          The <code>deploy</code> script first builds the project using <code>vue-cli-service build</code> and then deploys the <code>dist</code> directory to the <code>gh-pages</code> branch using <code>gh-pages -d dist</code>.
        </li>
        <li>Next, I configured the <code>vue.config.js</code> file to set the correct public path for the project:
          <pre><code>
module.exports = {
  publicPath: process.env.NODE_ENV === 'production'
    ? '/my-vue-project/'
    : '/'
}
          </code></pre>
          This configuration ensures that the project is served from the correct base URL when deployed to GitHub Pages.
        </li>
        <li>Finally, I ran the deployment script using <code>npm run deploy</code>. This command builds the project and deploys it to GitHub Pages, making the changes live.</li>
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
