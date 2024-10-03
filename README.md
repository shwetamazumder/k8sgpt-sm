
# Kubernetes with AI 

Hackathon 2024

# Problem

Pubsub+ Event Broker Kubernetes logs can be complex and requires expert knowledge to troubleshoot. Often the cluster logs does not have enough information to provide an immediate understanding of the problem and we need to use several other kubernetes cmds to ultimately find the root cause of the issue . This increases troubleshooting SLA. Furthermore, a running pod on a cluster may have some underlying issues which can get overlooked because they are not caught when we describe the pods. 

# Solution

A tool which constantly monitors the k8s clusters and reports on the event broker anomalies in simple english can greatly contribute in improving the troubleshooting experience and quality. 
As part of this project I have integrated an existing kubernetes tool , K8sgpt with AI model claude-3-5-sonnet. Integration with an AI model allows an user to understand the pod issues in simple english terms with guidance on troubleshooting steps. I have also integrated k8sgpt with grafana for visualizing the issues and with slack. Integrating with slack enables us getting a realtime alert in a chat interface further simplying the alerting process.


# Steps for building the model

Pre-requisites:

1. You should have a kubernetes cluster
2. Have kubectl installed
3. Have a slack webbook url for k8sgpt


Lets Begin:

1. Install k8sgpt from https://github.com/k8sgpt-ai/k8sgpt 
    a. Configure the CRD to enable AI access
    b. Enable grafana and Slack integration
2. Install Pubsub+ Event Broker from Solace Kubernetes Quickstarts at https://github.com/SolaceProducts/pubsubplus-kubernetes-quickstart
3. Introduce anomaly to event broker pods
4. Get notfied in Slack
5. Visualize the pods with anomalies in grafana
6. Use K8sgpt CLI to explain the anomaly by OpenAI and get guidance on the troubleshooting steps

# Future

Build a customer analyzer for K8sgpt with specific rules for Pubsub+ Event Broker monitoring