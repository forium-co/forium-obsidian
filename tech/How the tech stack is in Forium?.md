---
tags:
  - tech
---
All code and tech related stuffs will be discussed here.

So, Forium will have 3 main apps:
1. Web App
2. Mobile SDK
3. Desktop SDK (optional)

And a single server:
4. Zig server using libxev as the event loop. Helps in building a good enough framework for event loops and stuffs
5. SQLite and PostgreSQL integration with the user option to check

All of these 3 are white-labelled and can be integrated.

We are supposed to be lightweight and flexible.

We might end up going for the following technologies:
6. WebApp - Svelte
7. MobileApp - Flutter - easy to integrate into other apps. Make more s
8. Desktop (optional) - Tauri or Electron integration


These integrations make it quite easy for us to be in place of any app that we have. Easy for companies to manage their customer support without worrying about anything else.


# The Tech Stack

### Performance & Server Setup
9. Actix-web for Speed & Efficiency
    - Lightweight and fast framework for low-memory usage.
    - Perfect for hosting on small devices like Raspberry Pi or a $3 server.
10. In-Memory Data Cache
    - Built-in caching with Actix-web to reduce dependencies (e.g., Redis).
    - Option to disable if needed for server constraints.
11. Background Processes
    - Notifications: Email sending and summary generation.
12. Enterprise Features
    - Live reloads and real-time chat via WebSockets for instant updates.
### Database Support
13. RQLite (Distributed Database)
    - For standard users, a separate instance is spawned on each deployment.
14. SQLite + Litestream
    - Ideal for self-hosting and small communities.
    - Built-in streaming replication for redundancy.
15. Postgres
    - For production environments and heavy workflows.
    - Enterprise-ready with scalable setups.
### Web Frontend

16. Svelte
    - Server-side rendering (SSR) using Rust V8 for faster load times.
    - Service Worker and Mobile App SPA for offline-first experience.
17. Native-like Experience
    - Designed to feel as smooth as a native app.
18. Enterprise Features
    - Live reloads and real-time chat functionality.
### Storage
- S3 Integration
    - Default storage for images and files.
    - Option to disable for self-hosted solutions.