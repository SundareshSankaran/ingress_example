
## Basics - need for Ingress
1. First, know a K8s Service. Services route traffic using TCP/IP protocol.
2. Services, however, operate on known IPs and service names.  Service names are useful if internal communication is what's required, but these (and IP names) and ports need to be known in advance.
3. When used outside the cluster, NodePorts and LoadBalancer methods require prior knowledge of IPs. Also, lack a common standard pattern which makes it easy to interact with the same.
4. HTTP/HTTPS traffic abstract away the specificities required when interacting with services.
5. Annotations are arbitrary, non-identifying metadata.

## What is an Ingress?
5. K8s Ingress is an API object managing external access to services.
6. Uses rules to route traffic among services
7. Can be used with paths from a common FQDN
8. No need to know the name of the service - service can change under the covers.
9. Allows for SSL / TLS encryption

## Rules
10. Part of Ingress which defines how HTTP/HTTPS traffic should be routed.

## Example Ingresses
1. [This ingress](/example-ingress.yaml) has one path which routes traffic to a service called flask-service running at port 5000. 
  1. This is a root path (/) and therefore routes traffic which just call the host.
2. Using annotations, you can change properties.  These are dependent on the type of ingress controller you use.
3. This [example](/example-ingress-annotated-ssl.yaml) shows SSL annotations. 
4. This [example](/example-ingress-alb.yaml) talks about another ingress controller, ALB, and its annotations


## Architecture
1. Ingresses are at layer 7 of OSI model


## To dos:
1. Find out more about ALB

## Acknowledgements
1. Thanks, Tony, DevOps guy for this [article](https://medium.com/@tonylixu/devops-in-k8s-ingress-part-one-374baa00a0c7t)

