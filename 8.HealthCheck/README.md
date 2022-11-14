# Configuring Liveness, Readiness and Startup Probes
## Types
1. HTTP
2. TCP
3. Command line
4. gRPC
## Liveness Probe
- The kubelet uses liveness probes to know when to restart a container. 
- For example, liveness probes could catch a deadlock, where an application is running, but unable to make progress. 
- Restarting a container in such a state can help to make the application more available despite bugs.
### Steps for command line
- Writing pod kind yaml file and adding liveness in it
- Creating pod
    ```
    kubectl apply -f healthCheck.yaml
    ```
- after See events of pod
    ```
    kubectl describe pod healthCheckExec
    ```
- Getting list of pods to verify that it restarted
    ```
    kubectl get pod healthCheckExec
    ```    
## Readiness Probe
- The kubelet uses readiness probes to know when a container is ready to start accepting traffic. 
- A Pod is considered ready when all of its containers are ready. 
- One use of this signal is to control which Pods are used as backends for Services. When a Pod is not ready, it is removed from Service load balancers.
## Startup Probe
- The kubelet uses startup probes to know when a container application has started. 
- If such a probe is configured, it disables liveness and readiness checks until it succeeds, making sure those probes don't interfere with the application startup. 
- This can be used to adopt liveness checks on slow starting containers, avoiding them getting killed by the kubelet before they are up and running.