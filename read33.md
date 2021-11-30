# [reading-note-401](https://mohammadsilwadi.github.io/reading-note-401/)
## Assets, Metadata, and CSS
### Assets
Next.js can serve static assets, like images, under the top-level public directory. Files inside public can be referenced from the root of the application similar to pages.

The public directory is also useful for robots.txt, Google Site Verification, and any other static assets. Check out the documentation for Static File Serving to learn more.

### Download Your Profile Picture
First, let's retrieve your profile picture.

+ Download your profile picture in .jpg format (or use this file).
+ Create an images directory inside of the public directory.
+ Save the picture as profile.jpg in the public/images directory.
+ The image size can be around 400px by 400px.
+ You may remove the unused SVG logo file directly under the public directory.

```
<img src="/images/profile.jpg" alt="Your Name" />
```
### Using the Image Component
Instead of optimizing images at build time, Next.js optimizes images on-demand, as users request them. Unlike static site generators and static-only solutions, your build times aren't increased, whether shipping 10 images or 10 million images.

Images are lazy loaded by default. That means your page speed isn't penalized for images outside the viewport. Images load as they are scrolled into viewport.

Images are always rendered in such a way as to avoid Cumulative Layout Shift, a Core Web Vital that Google is going to use in search ranking.

Here's an example using next/image to display our profile picture. The height and width props should be the desired rendering size, with an aspect ratio identical to the source image.

Note: We'll use this component later in "Polishing Layout", no need to copy it yet.

import Image from 'next/image'

const YourComponent = () => (
``` 
 <Image
    src="/images/profile.jpg" // Route of the image file
    height={144} // Desired size with correct aspect ratio
    width={144} // Desired size with correct aspect ratio
    alt="Your Name"
  />
)
```

## Metadata
What if we wanted to modify the metadata of the page, such as the ``<title>`` HTML tag?

```<title>``` is part of the ```<head>``` HTML tag, so let's dive into how we can modify the ```<head>``` tag in a Next.js page.

Open pages/index.js in your editor and find the following lines:

```
<Head>
  <title>Create Next App</title>
  <link rel="icon" href="/favicon.ico" />
</Head>
```
Notice that ```<Head>``` is used instead of the lowercase ```<head>```. ```<Head>``` is a React Component that is built into Next.js. It allows you to modify the ```<head> ```of a page.

You can import the Head component from the next/head module.
Adding Head to first-post.js
We haven't added a ```<title>``` to our /posts/first-post route. Let's add one.

Open the pages/posts/first-post.js file and add an import for Head from next/head at the beginning of the file:

## import Head from 'next/head'
Then, update the exported FirstPost component to include the Head component. For now, we‘ll add just the title tag:

```
export default function FirstPost() {
  return (
    <>
      <Head>
        <title>First Post</title>
      </Head>
      <h1>First Post</h1>
      <h2>
        <Link href="/">
          <a>Back to home</a>
        </Link>
      </h2>
    </>
  )
}
```
## CSS Styling
Let’s now talk about CSS styling.

As you can see, our index page (http://localhost:3000) already has some styles. If you take a look at pages/index.js, you should see code like this:
```
<style jsx>{`
  …
`}</style>
```
This page is using a library called styled-jsx. It’s a “CSS-in-JS” library — it lets you write CSS within a React component, and the CSS styles will be scoped (other components won’t be affected).

Next.js has built-in support for styled-jsx, but you can also use other popular CSS-in-JS libraries such as styled-components or emotion.

Writing and Importing CSS
Next.js has built-in support for CSS and Sass which allows you to import .css and .scss files.

Using popular CSS libraries like Tailwind CSS is also supported.

In this lesson, we’ll talk about how to write and import CSS files in Next.js. We’ll also talk about Next.js’s built-in support for CSS Modules and Sass. Let’s dive in!

## React context
### What is React context?
React context allows us to pass down and use (consume) data in whatever component we need in our React app without using props.

In other words, React context allows us to share data (state) across our components more easily.
### When should you use React context?
React context is great when you are passing data that can be used in any component in your application.

These types of data include:

+ Theme data (like dark or light mode)
+ User data (the currently authenticated user)
+ Location-specific data (like user language or locale)
Data should be placed on React context that does not need to be updated often.
### What problems does React context solve?
React context helps us avoid the problem of props drilling.

Props drilling is a term to describe when you pass props down multiple levels to a nested component, through components that don't need it.
### How do I use React context?
Context is an API that is built into React, starting from React version 16.

This means that we can create and use context directly by importing React in any React project.

There are four steps to using React context:

+ Create context using the createContext method.
+ Take your created context and wrap the context provider around your component tree.
+ Put any value you like on your context provider using the value prop.
+ Read that value within any component by using the context consumer.