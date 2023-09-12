---
title: Testing Next.js 13 App Router architecture is... complicated
date: 2023-09-11
tags: ["blog", "nextjs", "next13", "jest"]
layout: layouts/post.njk
hasCodeblock: true
---

I've been trying to get back into coding daily and decided to start a side project using Next.js 13 new [**App Router**](https://nextjs.org/docs/app/building-your-application/routing#the-app-router) architecture — instead of the previous **Pages Router**.

The first red flag 🚩 I noticed was that there's no **Testing** documentation on the App Router docs. The second red flag 🚩 was that none of the examples in their GitHub repo, including the `with-jest` [template](https://github.com/vercel/next.js/tree/canary/examples/with-jest) updated in the first week of September 2023, has any examples of testing [React Server Components](https://nextjs.org/docs/app/building-your-application/rendering/server-components) which is the new paradigm the Vercel team is using in the **App Router** architecture.

When trying to test a RSC, React Testing Library throws an error `NEXT_RSC_ERR_CLIENT_IMPORT` as seen on this [issue](https://github.com/vercel/next.js/issues/47448) from May 2023. The Next.js team posted in early September 2023 that the canary version `v13.4.20-canary.16` fixes this error.

I've installed this canary version, and now the RSC I'm trying to test are returning `Objects are not valid as a React child (found: [object Promise])`. Yep, that's right: React Server Components can be async. They are safe to be async since they render on the server.

> If you want to know more about React Server Components, I recommend checking Josh Comeau's excellent post about it: https://www.joshwcomeau.com/react/server-components/

## Who isn't ready yet to test rendering async components? React Testing Library.

As more and more people jump in the Vercel hype train, RTL maintainers had to come with [workarounds](https://github.com/testing-library/react-testing-library/issues/1209#issuecomment-1569813305) to support that while they [try to reach the Vercel team](https://github.com/vercel/next.js/discussions/50479) to work together in a solution. Having an issue created in May 2023 without any response or emoji reaction from the Vercel team is unsettling.

The bottom line is that Vercel promoted to stable a "meta-framework" that comes short when handling unit testing coverage. I spent a day searching GitHub issues and connecting the dots from different repositories.

No one is warning developers about it or explicitly recommending creating or enhancing their end-to-end tests using Cypress or Playwright if they want to test their components. However, that's the solution maintainers are giving to their users.

## DX in detriment of quality?

What kind of message do meta-frameworks and libraries give to developers when they do such a thing? We already have non-semantic and inaccessible code propagated everywhere in docs, courses, and presentations.

We should worry about the code we put as a standard in our documentation and examples. Web semantics, accessibility, and testing should be part of the Definition of Done (DoD) of every code we write, not an afterthought.
