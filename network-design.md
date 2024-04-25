# Network Design with cilium

* Define metrics for risk exposure
* Focus on the most security sensitive namespaces first
* Leverage observability to identify which network policy patterns easily reduce risk with minimal friction
* Once tooling and policy management workflows are proven, use the metric to iteratively expand the covered workloads


* Start by** applying NP at namespace level**

## Risks to reduce 
* Intra cluster lateral movement
* Extra cluster lateral movement
* Data exfiltration

## Metrics to measure progress
* the idea is to Reduce mismatch between what is allowed by network policies

For example: 
* number of services reachable  via ingress / gateway api
* number of services reachable from other namespaces
* number of services with access to external network or internet

## Initial policies 

Start with two types of policies: 
* **Cluster wide policies:** same rules for every one; for example: 
  * allow access to dns service with port 53
  * allow access to monitoring (prom for ex) with port 9090
* **Namespace policies:** specific rules will be implemented by teams
  * Access to specific applicative services
  * access to internal network
 
Inspect your ingress / egress with hubble ui / cli
know where is your most exposed namespaces -> which namespaces have the most important traffic 


# Automation

![alt text](https://github.com/ozendorf/cilium/blob/main/network_policies_guardrails.png)

Automated checks in PR for teams submitted : 
* CIDR blocks
* egress to any
* allow flow on unsecure protocols related port (port 80)
* only allow specific fqdns and specific ips automatically

# Cilium features

ebpf = to kernel what javascript is to the browser
meaning it makes the kernel programmable in a dynamic and secure way

* Identity based security
* API aware authorization
* http aware cilium network policy
* dns aware network policies (s3 buckets for example)
* cluster wide network policies
* clusger mesh -> network policies accross multiple clusters
* hubble = hubble ui + hubble cli + hubble metrics
 * hubble metrics = builtin metrics for operation and application monitoring
 * hubble cli is more powerfull than ui
* network policy editor editor.cilium.io
* grafana for policy verdict metrics and to follow if you have implemented all network policy (mismatch monitoring)
