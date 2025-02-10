Forums should be lightweight and fast. Easily self-hosted and easily transferrable.

Low cost tech.
Make sure things are very modular. Its easy to build new features

Therefore we keep the following technologies in mind:
1. *Rust*:
	1. Single binary deployment.
	2. Fast to develop and fast apps
	3. Low latency and memory consumption. Lower cost when scaled.
2. *SQLite* & Postgres:
	1. For basic customers, we will provide hourly backups
	2. For premium, we will provide proper Postgres instances with 3 instances
	3. Databases will be colocated globally according to the company we are supporting.
	4. The home page database though will be distributed.
	5. Database load won't be an issue as we are decentralizing the app for multiple clients
3. *Svelte & SSR:
	1. Three builds:
		1. SSR builds for when first requested
		2. SPA builds for when the first requested 
		3. Webview build for Native mobile application
	2. Routes JS will be loaded async
	3. Every webpage excluding images should not exceed 50kB of contents. If 50Kb is somehow exceeded, check for optimizationa. It should be lightweight and fast. 
4. *TailwindCSS + DaisyUI*:
	1. Keeping it low-key, we focus on accessibility by hand rather than libraries. We keep our build server speeds very high with the lowest amount of dependencies
	2. This will be a tough one out of the following.
5. *Analytics & Logs*
	1. We start with Clickhouse DB
	2. To make it more self-hostable we use 
6. *Disk storage*:
	1. S3 compatible storage - Only thing that requires you to self-host separately
	2. Native FS (Self-host) - if S3 storage is not provided
7. AI
	1. Groq or Cerebras will be the first in mind. Cheap and useful for most clients
	2. Self-hosted options with Ollama available - another separate self-host thing
	3. Speed should be very fast for the AI to work well.
8. Ultralig.ht or Tauri as the two options for Desktop app
9. It should have a community of all things in this case.

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