# 🧩 Adapter Design Pattern

This design pattern should be used whenever the main container emits data in a certain format and the application to who the data should be sent to expects it in a different format. As the name suggests, the **adapter** container is here to **adapt**.

This is well-suited for log or monitoring management. Imagine a cluster with a lot of applications running. They are emitting logs in apache format and you want them in JSON to be sent to another application. This is where the **adapter** design pattern comes into play.

Just like the *sidecar* pattern, this can only work if both containers in the pod are accessing the same directory using volumes.

As with the ambassador and sidecar patterns, this one also needs *at least* two containers in your pod:
- Main container
- Adapter container
- .. other containers optionally

