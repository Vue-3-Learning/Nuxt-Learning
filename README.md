# Nuxt-Learning
Nuxt Js 
---
- [Introduction](#intro)
- [SetUp](#setup)
- [Project Structure](#project-structure)
---
## Intro
Nuxt.js is a powerful framework built on top of Vue.js, designed to help you build server-side rendered (SSR) applications, single-page applications (SPA), and static websites. Nuxt.js takes care of many things that you would normally have to configure yourself in a Vue.js project, such as routing, server-side rendering, and SEO.
Key Features:
- Server-Side Rendering (SSR): By default, Nuxt.js applications are server-rendered, which can improve SEO and performance.
- Static Site Generation (SSG): Nuxt.js can generate a static version of your application.
- Automatic Code Splitting: Nuxt.js automatically splits your code to improve load times.
- File-based Routing: Create pages simply by adding Vue files in the pages directory.
- Plugins and Modules: Easily add plugins and modules to extend your application.
- Middleware: Add custom functions to run before rendering a page.
## Setup
```
npx create-nuxt-app my-nuxt-app
cd my-nuxt-app
npm run dev
```
## Project Structure
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
