# Nuxt-Learning
Nuxt Js 
---
- [Introduction](#intro)
- [SetUp](#setup)
- [Project Structure](#project-structure)
- [Basic Concepts](#basic-concepts)
---
## Intro
Nuxt.js is a powerful framework built on top of Vue.js, designed to help you build server-side rendered (SSR) applications, single-page applications (SPA), and static websites. Nuxt.js takes care of many things that you would normally have to configure yourself in a Vue.js project, such as routing, server-side rendering, and SEO.
Key Features:
- Server-Side Rendering (SSR):Improves SEO and performance by rendering pages on the server before sending them to the client.
- Static Site Generation (SSG): Allows you to generate a fully static site that can be hosted on any static hosting service.
- Automatic Code Splitting: Splits your code into smaller chunks to improve load times.
- File-based Routing: Automatically generates routes based on the file structure in the pages directory.
- SEO Optimization: Easier to manage meta tags and other SEO-related configurations.
- Community and Ecosystem: Large community and many modules/plugins to extend functionality.
### What is npx?
npx is a tool that comes with Node.js, which allows you to execute packages from the npm registry without globally installing them. When you use npx create-nuxt-app, it downloads the create-nuxt-app package and runs it to set up a new Nuxt.js project.
## Setup
```
npx create-nuxt-app my-nuxt-app
cd my-nuxt-app
npm run dev
```
## Project Structure
```
my-nuxt-app/
├── assets/            # Uncompiled assets such as LESS, SASS, or JavaScript
├── components/        # Vue.js components
├── layouts/           # Layouts for pages
├── middleware/        # Middleware for pages or routes
├── pages/             # Vue files for each route
├── plugins/           # Plugins to run before rendering a page
├── static/            # Static files directly accessible via URL
├── store/             # Vuex store for state management
├── nuxt.config.js     # Configuration file
└── package.json       # Project dependencies and scripts
```
## Basic Concepts
### Pages and Routing
Nuxt.js uses a file-based routing system. Each .vue file in the pages directory automatically becomes a route.
Create a file called index.vue inside the pages directory:
```
<template>
  <div>
    <h1>Home Page</h1>
  </div>
</template>
```
This will create a route for the homepage (/).

Create another file called about.vue inside the pages directory:
```
<template>
  <div>
    <h1>About Page</h1>
  </div>
</template>
```
This will create a route for /about.
### Layouts
Layouts are used to define the common structure of your pages. By default, Nuxt.js uses the default.vue layout in the layouts directory.

Example:

Create a file called default.vue inside the layouts directory:
```
<template>
  <div>
    <header>
      <nav>
        <nuxt-link to="/">Home</nuxt-link>
        <nuxt-link to="/about">About</nuxt-link>
      </nav>
    </header>
    <nuxt />
  </div>
</template>
```
The <nuxt /> component renders the page component based on the route.
### Plugins
Plugins in Nuxt.js allow you to add custom functionalities to your application.

Example:

Create a file called myPlugin.js inside the plugins directory:
```
export default ({ app }, inject) => {
  inject('myInjectedFunction', () => console.log('This is an injected function'))
}
```
Then, register this plugin in nuxt.config.js:
```
export default {
  plugins: [
    '~/plugins/myPlugin.js'
  ]
}
```
You can now use the injected function in your components:
```
<template>
  <div>
    <button @click="$myInjectedFunction()">Click me</button>
  </div>
</template>
```
### AsyncData
asyncData is a special method in Nuxt.js used to fetch data before rendering a page.

Example:

In the pages/index.vue file:
```
<template>
  <div>
    <h1>{{ title }}</h1>
  </div>
</template>

<script>
export default {
  async asyncData() {
    const data = await fetch('https://jsonplaceholder.typicode.com/posts/1')
    const post = await data.json()
    return { title: post.title }
  }
}
</script>
```
This will fetch the post data before rendering the page and set the title data property.
