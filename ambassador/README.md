# 🧩 Ambassador Design Pattern

The ambassador desgin pattern applies to multi-container pods. We can define two containers in the same pod:
- Main container
- Ambassador container

In this design pattern, we assume that the main container might have access to external services to communicate with them. For example you can have an application that must interact with a SQL database that is living outside of your cluster.

The ambassador container comes in, essentially as a proxy (or middleman) between the external dependency (which here is the database) and our application.

Keep in mind not to add ambassador containers unless your dependency is outside the cluster, since in the case when it's in the same Kubernetes cluster there is a more powerful mechanism (K8s services)

Some benefits are:
- Offloading SQL configuration in this case

> ❗️ Please note that although this is just an example, the ambassador container should never be considered an entrypoint to the cluster, but it should only be called from the main container for an outbound connection to something external of the cluster.
