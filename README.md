# Forium
> Connect, DIscuss & Thrivve

A community engagement platform for all.

Forium is an open source forum SaaS that is designed to:
- Self-host
- Performant & Fast
- Cheap pricing
- Beautiful UI/UX

Features wise, Forium is nothing but a clone of Discourse, with the exception of it being super sleek and fast. Today all open source software lack that super speed and good UX both of which makes an app what it is today. 

Since, we are aiming for a very specific goal, we can safely lay out the features to implement and turn the knobs on to improve performance.

# Tech stack

So, first of all, let's look at performance:
1. Use Actix-web for speed and low-memory usage. A dude with an RPi or a $3 server somewhere should be able to host the server without any issue.
	1. An in-memory data cache with actix-web to act without redis. With an option to turn off the in-memory if you want to host with server constraints.
	2. Background process:
		1. SQLite `VACCUUM` & periodic backup
		2. E-mails and summaries
	3. (Enterprise) Live reloads and chats (Websocket based live updates)
2. Support for three databases:
	1. RQLite distributed
		1. For Standard users, this will be spawned separately on each deployment
	2. SQLite & litestream
		1. For self-hosting and small communities
	3. Postgres -  For production and serious workflows
		1. For Enterprise this will be 
		2. For basic users, just one instance will 
3. Use SolidJS on the web with:
	1. SSR rendered app as the base rendered using `rust_v8`
	2. Service Worker and Mobile App SPA (without any prefilled data)
	3. Should feel as much native as possible
	4. (Enterprise) Live reloads and chats
4. S3 as storage for images (can be turned off if the user wishes to (self-host))

These tech choices will enable us to write a great app without much constaints.

# Pricing

Tech choices aside, our features are very limited to Discourse. Just make a better Discourse is all we are going to do and that too cheap. Pricing can be of the following:
1. Starter
	1. Free ($0)
	2. 500MB of storage
	3. 50k posts & comments views/month
	4. Custom domain
	5. No integrations
	6. No customization
	7. E-mail, google and twitter logins
2. Standard
	1. $50/mo
	2. 20GB of storage
	3. 500k posts/comments per mo.
	4. Unlimited Staff
	5. Discord and Reddit integration (reddit is pay per use though and may vary)
	6. All other logins (Discord, google, facebook, github, twitter, apple, Microsoft)
	7. Basic AI
	8. RQlite based 3 instances
	9. Addons:
		1. Reddit integration (pay per use). Turn on to sync (might cost a lot)
		2. PostGRES database ($50)
		3. More instances ($20/instance) for faster responses
	10. ...provide almost all enterprise features that discourse provides here.
	11. Custom bots and plugins support (All https://discourse.org/plugins)
	12. SDK (100k/month)
	13. Theme generator (For both dark and light mode)
	14. Custom CSS
	15. Community Support only
3. Enterprise (Contact Us) - ($2000/month)
	1. Everything is unlimited
	2. Postgres based instances per user
	3. Multiple deployments of servers.
	4. Priority Support

Since, I am working on a constraint and the majority of the earnings will be from Standard users, I will have to squeeze the cost for everything.