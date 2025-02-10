---
tags:
  - rfc
  - authentication
---
Authentication requires us to think about how fast can we enable users to join the forum.
Users should be able to quickly go to a link and if logged in through the parent website, should be logged in here as well. That's it.

This easy integration has to be written well and proper in tutorials.

Some of the stuffs that we will be discussing here:
- User Authentication
- OAuth Authentication
	- We provide OAuth Authentication to every user to get the basic necessary details for them
	- Like let's say we are building a forum for OpenAI, we will ask the users to sign-in using OpenAI credentials.
	- We redirect OpenAI to a particular page where the users can simply visit. If logged in, a secret code will be received to our servers, which will give us details about the user
		- e.g. Github authentication for the desktop app


In this RFC we will be discussing the above. More information will be clear once I implement the above.

This is the basis of our app and what makes us special.