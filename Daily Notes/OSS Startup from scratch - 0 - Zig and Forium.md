---
tags:
  - blog
  - zig
  - http_server
date: 27 Sep, 2024
---
So, I learnt Zig and wrote some interesting repos:
- [GitHub - Himujjal/zig-json5: A JSON5 parser/stringifier for Zig resembling the std.json API](https://github.com/Himujjal/zig-json5)
- Attempt at a TypeScript parser in Zig: [GitHub - Himujjal/ts-parser-zig: A Handwritten TypeScript parser in Zig](https://github.com/Himujjal/ts-parser-zig)
- Attempt at a Svelte/HTML parser in Zig: [GitHub - Himujjal/svelte-parser-zig: A hand-written parser for Svelte in Zig](https://github.com/Himujjal/svelte-parser-zig)
- Attempt at a CSS Parser in Zig: [GitHub - Himujjal/css-parser-zig: A SCSS/CSS Parser in Zig](https://github.com/Himujjal/css-parser-zig)

That being said, I am not in much of a state to experiment. I recently became Head of Engineering at [Wokay](https://wokay.com) and have more work to do.
But my itch of making [EkScript](https://ekscript.com) hasn't gone yet. That is for far later. Zig used quite often with a JavaScript engine.

That being said, I am now done with these toy projects. I want to start a serious project and achieve that goal with Zig as much as possible.
I want a project that people use daily and achieve that goal by writing everything from scratch.

So, I decided to build **Forium**. Forium is a discourse clone. A forum software but with a 2020+ feel to it. It will be built in a Zig server written from scratch.
Yes! From scratch. I love front-end development. I love good design. So, I will be treating this project with a really beautiful thought out design as well.

Yes! The second part of the project will be about Svelte and making native looking UI for it.

And if the project goes well. I want to host [ziggit.dev](https://ziggit.dev) on Forium.

### Why Zig?
- First. I want to get into the ins and outs of a powerful systems programming language. I think Zig is simple to use if you know what you 
- Second, I want it to be lightweight. 
- Third, I have the chance to create a truly full-stack web-app framework SSRd with Svelte.
- Fourth, I want to test Zig in a truly production heavy non-systems app. How good does this language serve me?

### Why Svelte?
- I love Svelte!
- I want to try out RSBuild with Svelte and SSR with Zig.

# Forium
- A Discourse community clone that serves the purpose of a blog post aggregator for a community and a forum to go with it.
- It will like a social media but more fun beatiful.
- Its server will be almost from bare minimum dependencies
- Let's build it.
- Forium only supports one community. Or multiple workspace based on the settings
	- Multiple community will be more like a great thing to have as well.
	- For example, Zig can have Embedded Group as a separate community
	- Microsoft can have Azure, Windows or Surface section
- Forium should be self-hostable Discourse but better UI/UX and in Zig. So, lightweight, baby!

# The plan
So? From scratch.

Let's make a plan:

## Step 1 - : - Copy http.zig library
## Step 2 - : - Copy websocket.zig library
## Step 2.1 - : - Start building TailwindCSS theming engine in RSBuild and Svelte
## Step 3 -:- Build a V8/QuickJS bridge for SSR.
## Step 4 -:- Copy Zqlite and join it with http.zig clone
## Step 4.1 -:- Make it distributed like Marmot 
## Step 5 -:- Auth layer - Forium - Zig and Svelte
## Step 6 -:- Forium Feed
## Step 7: Forium Admin Settings 
## Step 8: Other Forium app 
## Step 9: Bringing Forium to Desktop with WebUI zig from scratch
## Step 10: Bringing Forium to Mobile with Capacitor
## Step 11: Forium landing page  
## Step 12: Forium infra and self-host

That's it folks!

---
Let's start. We will first create `http.zig` and then move on to the next steps. Let's build Forium.