Forium should be easy to self-host. Either on a single machine or a host of other machines.

So, for standard plan, we will provision 1 set of servers (5 locations) to 20 clients.

($50/client * 20 clients = $1000) - ($30 / server * 5 servers = $150) - ($50 misc) = ~$800 / 20 clients = ~$40 profit / client

This gives us a high profit margin simply based on our infra cost. Therefore success of the server is necessary for this.

Later based on usage, I would say, we can actually run 100 standard clients on the same server without sweat which means ($50 * 100 = $5000) - ($100 * 5 = $500 / month) = $4500 / month from 100 clients (Rs. 3.6 lakh). 

For standard clients we give S3 storage as well as mellisearch which gives

Only enterprise users will be able to access the Production server (cost: $100/month) for a profit of ($500/month). $400/month profit from 1 enterprise customer.

The ability to be flexible on a range from full-hosting on a single device to replicated hosting to fully micro-service based hosting gives Forium the ability to scale according to clients.

To make the most out of Forium, you need to provide features as well:
- AI search
- UI/UX should be awesome and not some 2000s bullshit
- Fast load times using SSR, SW and SPA and lightweight pages. No bundling to save page size
- Analytics should be fast
- Discord/Discourse/Reddit integration
- Tauri App (Desktop & Mobile) for engagement (Easier to maintain too as the whole thing will run off the web anyways)
- Translate for feature
- Announcements
- Native SDK for apps and websites
	- Use the same login to make sure that the whole app can be easily embedded with the current login.
	- React Native, [Integration with Existing Apps · React Native](https://reactnative.dev/docs/integration-with-existing-apps?language=kotlin)
	- Auth hooks to let the users login with the same account.
		- Cookies
		- JWT based
	- Should look like its a part of the project