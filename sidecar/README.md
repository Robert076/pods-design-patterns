# 🧩 Sidecar Design Pattern

The sidecar container is an extension or a helper for your main container. It is used to extend the main container by bringing it a new feature but without changing the main container.

The sidecar design pattern contains:
- Main container
- Sidecar container

This pattern is especially useful for when you want to run monitoring or log forwarding agents.

There are three things you need to understand when you build a sidecar container that is going to forward your logs to another location:
- You must locate the directory where the logs are stored by the main container
- You must create a volume to make this directory accessible from the sidecar container
- You must launch the sidecar with the proper configuration

Based on these concepts, the main container remains unchanged and even if the sidecar fails it wouldn't impact the main container.

> ❗️ This is different from the ambassador container as the main container might not even know that this sidecar container exists, whereas in the ambassador design pattern it was used as a proxy and the main container knew about it. Make sure not to confuse the two as they have different purpose. The sidecar adds a functionality and the ambassador serves as a proxy from inside the main container to an outside dependency.
