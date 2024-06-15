# Rasengan MDX Plugin

[![npm version](https://badge.fury.io/js/@rasenganjs%mdx.svg)](https://badge.fury.io/js/@rasenganjs%mdx)
![NPM Downloads](https://img.shields.io/npm/dm/%40rasenganjs%mdx)
[![GitHub license](https://img.shields.io/github/license/rasengan-dev/rasengan-mdx-plugin)](https://github.com/rasengan-dev/rasengan-mdx-plugin/blob/main/LICENSE)

MDX plugin for Rasengan.Js

## Installation

You can install the `@rasenganjs/mdx` package using the following command:

```bash
npm install @rasenganjs/mdx
```

or

```bash
yarn add @rasenganjs/mdx
```

## Usage

Here is an example of how you can use the `@rasenganjs/mdx` package:

### Basic Usage

1. Setup the `rasengan.config.js` file

Import the `mdx` plugin into the `rasengan.config.js` file.

```javascript
import { defineConfig } from "rasengan";
import mdx from "@rasenganjs/mdx";

export default defineConfig({
  reactStrictMode: true,

  // Define aliases
  vite: {
    plugins: [
      mdx(),
    ],
  },
});
```

2. Create your `markdown` file.

Create a `markdown` file inside the `app` folder with the pattern `[name].page.mdx` or `[name].page.md`

```mdx
---
path: /blog
metadata:
  title: Blog page
  description: Discover our new blog posts
---

import Button from "@/components/Button";

# Blog page

This is a `blog` page.

<Button>Click Me</Button>
```

3. Use your `markdown` file.

Inside the `app.router.ts` file, import your Markdown Component and the `generatePage` function from `@rasenganjs/mdx`

```typescript
import { RouterComponent, defineRouter } from "rasengan";
import AppLayout from "@app/app.layout";
import Blog from "@app/blog.page.mdx";
import { generatePage } from "@rasenganjs/mdx";

const BlogPage = generatePage(Blog);

class AppRouter extends RouterComponent {}

export default defineRouter({
  imports: [],
  layout: AppLayout,
  pages: [BlogPage],
})(AppRouter);
```

Now visit [http://localhost:5320/blog](http://localhost:5320/blog)

## Community

The Rasengan.js community can be found on [GitHub Discussions](https://github.com/rasengan-dev/rasenganjs/discussions) where you can ask questions, voice ideas, and share your projects with other people.

We also have a [Twitter](https://twitter.com/rasenganjs) account where you can follow us to get the latest news about Rasengan.js.

## License

Rasengan.js is [MIT licensed](https://github.com/rasengan-dev/rasengan-image/blob/main/LICENSE).

## Authors

Here is the authors list:

- Dilane Kombou ([**@dilanekombou**](https://twitter.com/dilanekombou))