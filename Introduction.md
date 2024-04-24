# Introduction
https://www.youtube.com/watch?v=80OYrzS1dCA

cilium = next gen cloud network and security technology
ebpf was invented to tackle the problem of innovation in linux by extending the linux kernel capacities
usage of ebpf: 
* traffic accounting is using ebpf
* google with ebpf 

tcpdump uses bpf (original berkeley packet filter tool)

`cilium install`
will install a daemon set agent and an operator
cluster role, service account, configmap, some secrets, 

`cilium connectivity test`

will deploy a test namespace and some pods to run connectivity tests

`kubectl exec -ti pod_name -- bash` to get a bash on the pod

`cilium endpoint list`

`cilim bpf`

`cilium bpf endpoint list` to see kernel mapping with endpoint (cilium pods)

Cilium can manage anything tht is represented by a cgroup or a network device 

`cilium service list`to list all the services cilium implement
and to see the kernel view of this:  `cilium bpf lb list`

`hubble port-forward`to see communication between nodes (like tcpdump)


## Links
* https://github.com/isovalent/eCHO/tree/main/episodes/001
* https://editor.networkpolicy.io/


## To read
* https://www.grant.pizza/blog/vmlinux-header/
