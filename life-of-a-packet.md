# Introduction

https://docs.cilium.io/en/stable/network/ebpf/lifeofapacket/#life-of-a-packet

L7 policy = policy to allow traffic between two applications (client and server for example) based on url (/api/v1 for ex) 

debugging kubernetes with crictl

nsenter command executes program in the namespace(s) that are specified in the command-line options

What cilium does is instrumenting an interface to put traffic control connection on the interface. That's where we write the ebpf program.

![image](https://github.com/ozendorf/cilium/assets/50991080/5eeced7c-65d5-4024-af54-ed48bf6faeb2)

ethtool is used to query and control network device driver and hardware settings, particularly for wired Ethernet devices

to get a bash interface on a pod : 
```kubectl exec -ti "pod_name" bash ```
