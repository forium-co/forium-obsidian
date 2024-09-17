
Front-end will have two parts:
- SSR based templates
	- this is for quick access
- Templates with blank space for dynamic content (with boot time for syncing settings)
	- This has the SPA native feel to it.
	- Boot call will update the local storage with the latest values and state
	- Then the data will be loaded accordingly (which was previously loaded with Zig SSR) now will only have JSON responses to fill

This should be super-fast in all aspects!