---
tags:
  - rfc
  - engineering
---
Social Media is generally not offline first. But we can figure out that many posts are in fact so.

Considering user interactivity we can also pre-fetch a lot of the posts beforehand and just render them as if they are native.

This gives us a considerable advantage when showing pages. This will also mean that every post/comment etc will have a loading state in the global store itself.

Another problem is cache invalidation. We will denote everyone as offline when there is no network and do a retry thing. We won't allow offline updates and disable it.

But we must provide users draft option. Every comment, every post etc can be a draft and should be shown as such, so that when the user is back online, they can use it.

Boot calls will be light as we will have to quickly render the SSR page.