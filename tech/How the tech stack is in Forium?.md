---
tags:
  - tech
---
All code and tech related stuffs will be discussed here.

Currently the Forium tech stack looks like:
1. Design
	1. Figma
	2. Spline
	3. Some cool AI tools
2. Front-end:
	1. React, Zustand, React Query
	2. Radix, Tailwind, ShadCN
	3. Replicache
3. Back-end
	1. Phoenix
	2. SSR based framework
4. Database:
	1. SQLite & PostGres (main)
	2. DuckDB & Motherduck for Analytics & logs
	3. RocksDB for cache (this is permanent)
	4. Simple Queues on top of SQLite and PostGres
	5. S3 based backup
5. Infra and CI/CD
	1. Github actions
	2. Grafana
	3. OVH or other cheap VM providers
	4. S3 or Backblaze