Forums should be lightweight and fast. Easily self-hosted and easily transferrable.

Low cost tech.
Make sure things are very modular. Its easy to build new features

Therefore we keep the following technologies in mind:
1. *Go*:
	1. Single binary deployment.
	2. Fast to develop and fast apps
2. *SQLite* with eventual consistency:
	1. A marmot like model
	2. Regular back-ups
	3. Make it quick with eventual consistency
	4. Multi-SQLite servers
1. *Svelte & SSR:
	1. Two builds:
		1. SSR builds for when first requested
		2. SPA builds for when the first requested 
	2. Routes JS will be loaded async
	3. Every webpage excluding images should not exceed 50kB of contents. If 50Kb is somehow exceeded, check for optimizationa. It should be lightweight and fast. 
2. *TailwindCSS + DaisyUI*:
	1. Keeping it low-key, we focus on accessibility by hand rather than libraries. We keep our build server speeds very high with the lowest amount of dependencies
	2. This will be a tough one out of the following.
3. *Analytics & Logs*
	1. We start with Clickhouse DB
	2. To make it more self-hostable we use 
4. *Disk storage*:
	1. S3 compatible storage - Only thing that requires you to self-host separately
	2. Native FS (Self-host) - if S3 storage is not provided
5. AI
	1. Groq or Cerebras will be the first in mind. Cheap and useful for most clients
	2. Self-hosted options with Ollama available - another separate self-host thing
	3. Speed should be very fast for the AI to work well.
6. Ultralig.ht or Tauri as the two options for Desktop app
7. It should have a community of all things in this case.

## Self-hosted

- [ ] Forium should be open source
- [ ] Forium should be self-hosted by default without much difficulties. No infra tension. Just start the app on a server and you are done or customize your way to a production app.
- [ ] Proper one-click deploy for those who want to start quick with self-hosting
- [ ] No self-hosted app will be this fast

## Everything is fast in Forium 
- Speed of development
- Speed of page loads
- Large traffic handling
- Zero to self-host in 2 minutes (in a $5 VM) or use Fly.io