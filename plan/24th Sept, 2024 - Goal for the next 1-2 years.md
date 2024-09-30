So, I am the head of engineering and product at Wokay. So, this project will take at least 1 year to build. Be patient. You can be patient and build it as a side-project. You know what to do. I love myself. 

And I won't be having time to build Forium and maintain it as a business. That I will have to do later in 30th Sept, 2026. That day I will publish Forium. But with the following:

So, I am still going to build Forium in Zig and a little bit esoteric, but I have to keep the burden low. So, I have decided to do the following:

1. HTTP Server -> Zig
	1. Copy http.zig from karlseguin
2. Marmot Go like Distributed SQLite in Zig
	1. zqlite from karsequin and add raft to it
3. Front-end
	1. RSBuild and Dev-server based Zig server
		1. This is much easier to achieve. Mostly trial and error.
	2. Svelte with SSR rendering using Zig V8 and [Svelte-routing](https://github.com/EmilTholin/svelte-routing) SSR
		1. zig-v8 by fubark
	3. Custom themes for all 6 platforms.
4. WebUI for MacOS, Linux, Windows, Android and iOS - Very lightweight and fast! That's the goal.
	1. Your only aim here is to be iOS and Android compatible. That you can tackle.
	2. Make custom native themes for all the platforms in CSS/TS. The Native themes for all the platforms should be the default.
	3. Don't try to change the placement of stuffs. Just make the style, fonts, animations and colors similar

This is important. Why? Because the ability to actually make a production ready web-app in Zig is not ready yet and this is going to make it possible.

The goal is to obliterate Zig Discord, Zig guide, ziggit.dev and zig.news altogether within one platform. That will be my biggest contribution to ZSF. Focus on the goals.

Later on, I will make it into a complete framework for all SaaS to host their communities in. First let's target the OSS group.

## V2 - don't do:
Okay. So, I am not creating Front-end from scratch. That 's just nuts. There are better tooling and the eco-system is vast.

- EkScript based Front-end and bundler
	- EkScript both in the back-end and front-end
	- EkScript bundler and Tailwind
- EkSwara based Web cross platform.
	- HTML/CSS/EkScript dream, without JS and the bloat involved.

What I am going to target specifically is the Front-end crowd saying: See. Zig is such an easy language to write in. You have been missing a lot

So, [[The marketing perspective]] of leveraging Zig in the front-end web-app wasm world will work wonders, thus bringing in more users. Forget about inefficient Zig. Some techno-wizard will improve the ORM. He will fix the server speeds. You just have to give the people a platform to work on.

So, bring Zig to the web and AI. That's the goal!