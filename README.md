# hydra-cloud-scale

## Blueprint
As APIs developers may want to deploy a Hydra-based servers/agents system on the cloud, it is provided here a tool to easily structure the content of Hydra specification documentation (`ApiDoc`) as a distributed cluster using a Docker stack.

Briefly, it should be possible to create a cluster from any compliant `ApiDoc` and deploy a docker container for each `HydraClass` in the document, so to create a "microservices-like" environment on which to plug a compliant agent (like `hydra-python-agent`). The agent would act as the tool to query the relationships among classes at scale. One agent, many hydrus servers that represent the data model; to query this distributed model, every agent connected stores the graph and runs query on its graph store.

Practically:
* the `ApiDoc` is destructured into its `HydraClass`es and for each of them a hydrus instance is spawned
* every authorised agent (`hydra-python-agent`) can connect to the cluster, build its own data graph and run queries and receive data updates.

## Local test implementation

Proposed implementation is to use Apache OpenWhisk. OpenWhisk is a portable serverless framework that works on top of popular technologies like Docker (i.e. Docker-On-Docker) and Kubernetes.

### Prerequisites
* install Docker and latest stable version of GoLang
* install [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-binary-with-curl-on-linux)
* install `kind` (GoLang library, only used for local development) following [these instructions](https://kind.sigs.k8s.io/docs/user/quick-start/#installation)
* install [OpenWhisk wsk CLI](https://github.com/apache/openwhisk-cli#compile-the-binary-using-your-local-go-environment)
* install [OpenWhisk wskdeploy](https://openwhisk.apache.org/documentation.html#wskdeploy)

### Create a local environment

Follow [this instructions](https://github.com/apache/openwhisk-deploy-kube/blob/master/docs/k8s-kind.md#deploying-openwhisk-on-kind) to create a local cluster
 
