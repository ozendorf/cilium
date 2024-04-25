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

![alt text](https://github.com/ozendorf/cilium/blob/main/network_policies_guardrails.png)
Some 
# Automation
