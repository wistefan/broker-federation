# Broker-Federation

> :warning: This is not intended for production usage. In order to evolve it for such, passwords and ssl need to be properly configured on the
> brokers and databases. Additional, backup and replication needs to be taken into consideration.

Gitops repository to showcase federation between different NGSI-LD context brokers(e.g. Orion-LD, Scorpio and Stellio)

The setup holds installations of all three brokers, together with their databases:

* [Orion-LD](https://github.com/FIWARE/context.Orion-LD) with MongoDB
* [Scorpio](https://github.com/ScorpioBroker/ScorpioBroker) with Posgres and Kafka
* [Stellio](https://github.com/stellio-hub/stellio-context-broker) with Neo4j, Timescale and Kafka

All components are installed using a GitOps-Approach based on[ArgoCD](https://argo-cd.readthedocs.io/en/stable/). The cluster and its setup guide can be found at [FIWARE-Ops/fiware-gitops](https://github.com/FIWARE-Ops/fiware-gitops).
Following the app-of-apps pattern, an umbrella-chart template the ArgoCD-applications is used. The application can be found in the [app-of-apps folder](app-of-apps/). The broker configuriations are located at the [brokers-folder](brokers/). They use a combination of helm-charts and plain manifests:
* [Orion-LD](brokers/orion-ld/) 
* [Scorpio](brokers/scorpio/)
* [Stellio](brokers/stellio/)
