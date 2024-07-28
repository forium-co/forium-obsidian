TL;DR - to quench my NIH

The biggest question here is why am I doing all of these?

I want to make a solution for individuals to host their web application without worrying about scaling. SImply open another instance and run the application in the most fastest way possible.

This is also to quench my NIH thirst.

The application should be one process only so that it could run off something like Busybox image without needing multiple processes. the ultimate guide to writing a web server in a single executable in a single process.

Its made up of optional stack of components which can be used together or separately as per users' choice:
## Kubernetes and docker
- Kubernetes
	- Add multi-cluster of this application and monitor
- A docker with busybox allowing nothing but the app to run in the container
- Kubernetes should automatically open ports for local connection
- Volumes can be streamed 

## Load Balancing & Security

- The app connects directly to `localhost:80` and `localhost:443` depending upon whether you want `http` or `https`
	- Caddy like functionality without needing a separate process
	- DDoS protection
	- HTTP encryption
	- HTTPS TLS certificates auto-generated with just a single command using OpenSSL 
	- Network queue for when the application is busy

## Zig server
The main app starts with a threadpool with requests following routing algorithm to ditribute loads between threads.

## Database
The database under the hood is SQLite (with replication functionality)
- With Raft algo and protocol
	- `zraft` library
- DQLite clone
- Replicates to nodes that connects to it.
- No master and consensus based writes.
- All statements are prepared when the Database inits. Custom unprepared statements are also supports
- Thread collocation:
	- Single writer connection in a thread
	- All read connections are in the queue (to avoid retries) with each read connection across the application threads. No thread switching unless you are writing
- Functionality to detect whether write is going to happen beforehand
- Periodic backups facitility

## KV Store - in memory
- Simple Hashmap in a struct with predictable data structure
- Atomically locked and globally available
- Runs in the main thread. Clones data

## File Storage
- Its better to keep file storage separate as another server or process though as replication is a tough nut to crack
- That being said. We will have a way to run the whole thing in a single server using the native file system
	- Backups for the file system has to be done from the cloud provider side
	- A streaming replication method will be also provided for the backup process that allows the server to backup files to another server/s3
		- as a separate process
		- in the same process.
	- backups will have an interval
- Folder wise replication facility (Works as a CDN as well!). This configuration can allow the devs to not use a CDN at all and simply use the server to create a CDN like replicated storage.

## Analytics
- Use DuckDB
- All data coming in are appended as `.parquet` in a streaming manner to:
	- S3
	- Local file
- We can then write queries using DuckDB in a separate thread when the requests come in from the HTTP server.
- These files that we write can be of different metrics
- Simple operation for write. DuckDB for read
- `Logging` can also be done similarly in NDJSON to parquet file and then use DuckDB to analyze the data
- Front-end for the analytics should provide a DuckDB analytics method


The tools we are using that are already present:
- Kubernetes
- Linux containers
- Zig
- SQLite
- DuckDB
- Garage.fr for hosted options
- Infra wise, I would require if at max:
	- 3 servers - connected. 1 server at minimum
	- Replication for files will be asynchronous and exceedingly simple


## Front-end

Now, this is a thing I wanted to do.
I think MPAs are the best at what they do. Just that distributing them and reusing templates are a hard thing.
I think MPAs, SSR, CSR and Service-workers in combination is the best solution there is for writing fast web applications.
Its fine for the whole page to load or load partially. Data persistence between pages can be done through simple Svelte Storage like thing.

App shells can be used for PWA.

This process has a few challenges:
- SSR rendering will require JavaScript on the back-end (Can remove that with WASM and EkScript)
- SPA mode will also be supported by EkScript