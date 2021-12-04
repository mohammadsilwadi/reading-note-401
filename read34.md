# [reading-note-401](https://mohammadsilwadi.github.io/reading-note-401/)
## Dynamic Routes
In Next.js you can add brackets to a page ([```param```]) to create a dynamic route (a.k.a. url slugs, pretty urls, and others).

Any route like /post/1, /post/abc, etc. will be matched by pages/post/[```pid```].js. The matched path parameter will be sent as a query parameter to the page, and it will be merged with the other query parameters

For example, the route /post/abc will have the following query object:

{ "pid": "abc" }

dynamic routes are handled with next/link

```
import Link from 'next/link'
  <Link href="/post/abc">
          <a>Go to pages/post/[pid].js</a>
        </Link>
```

### Catch all routes
Catched parameters will be sent as a query parameter (slug in the example) to the page, and it will always be an array, so, the path /post/a will have the following query object:

```
{ "slug": ["a"] }

And in the case of /post/a/b, and any other matching path, new parameters will be added to the array, like so:

{ "slug": ["a", "b"] }
```
## Next.js - Deployment
### Vercel
Vercel is A cloud platform for serverless deployment. It enables developers to host websites and web services that deploy instantly, scale automatically, and require no supervision, all with minimal configuration. Vercel is a tool in the Static Web Hosting category of a tech stack.

In this url you can see my react application
[my website](https://cookie-stand-admin-adavpn6zl-mohammadsilwadi.vercel.app/)
