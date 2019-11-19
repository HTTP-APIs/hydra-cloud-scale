# hydra-cloud-scale

## Blueprint
As APIs developers may want to deploy a Hydra-based servers/agents system on the cloud, it is provided here a tool to easily structure the content of Hydra specification documentation (`ApiDoc`) as a distributed cluster using a Docker stack.

Briefly, it should be possible to create a cluster from any compliant `ApiDoc` and deploy a docker container for each `HydraClass` in the document, so to create a "microservices-like" environment on which to plug a compliant agent (like `hydra-python-agent`). The agent would act as the tool to query the relationships among classes at scale. One agent, many hydrus servers that represent the data model; to query this distributed model, every agent connected stores the graph and runs query on its graph store.

Practically:
* the `ApiDoc` is destructured into its `HydraClass`es and for each of them a hydrus instance is spawned
* every authorised agent (`hydra-python-agent`) can connect to the cluster, build its own data graph and run queries and receive data updates.

PS. we are looking for a devops expert to support our mentors and students to realise this project, [Join our Slack](https://join.slack.com/t/hydraecosystem/shared_invite/enQtNzM3NTg5NzQ2MDUxLWU1MjM3ZGRhZWM4ZTg1ODBjMTljNTQwNzAwMGM3ZDlmYTY3Y2E4OGJmN2NlZWRjMWIzY2MzN2NjOTIyYmQ1ZjU) and drop a message (:
