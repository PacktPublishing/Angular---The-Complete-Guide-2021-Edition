Angular Universal Gotchas
You typically use Angular Universal to pre-render Angular pages on the server. Once the app then runs on the client, it's a normal SPA again.

Server-side rendering (SSR) can make sense because of SEO considerations (crawler should see what your users see) or because you want to deliver a finished page to your users (rather than creating the page in the browser).

But that also has one important implication: You MUST NOT use any browser-only APIs like document.querySelector()  in your Angular code! 

Simply because it will execute on the server and there, such APIs are not available.

That's why, in this course, I recommended to use Angular features only: These features are safe to use because Angular will check if a certain API can be used before it uses it.