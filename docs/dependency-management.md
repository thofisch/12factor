# Dependency Management

A {==cloud-native/Kubernetes/"cloud-friendly"==} application must be self-contained, where everything we need to run our application is contained within a single build artifact. Applications can no longer assume that a server will have everything they need. Instead, applications need to bring their dependencies with them.

E.g., never rely on the implicit existence of system-wide packages, or facilities like the Global Assembly Cache.


!!! tip "Repeatable deployments"
    Managing application dependencies is all about repeatable deployments.
    
    Nothing about the runtime into which an application is deployed should be assumed that isn’t automated. 

## Kubernetes

Fortunately, it is relatively easy for the container to include all of the dependencies on which the application relies, and provide a reasonably isolated environment in which the container runs. {==(container environments are not completely isolated, but for most situations, they are Good Enough.)==}

For applications that are modularized and depend on other components, Kubernetes provides a way to combine all of these pieces into a single Pod, for an environment that encapsulates those pieces appropriately.
