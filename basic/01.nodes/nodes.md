# 集群节点
TODO: create kubeadm cluster

# 获取k8s集群node节点
```
kubectl get pods -A
```

# 查看node节点信息
一个节点的状态包含以下信息:

地址（Addresses）
状况（Condition）
容量与可分配（Capacity）
信息（Info）
```
kubectl describe node ${nodeName}
```
[详细信息参考](https://kubernetes.io/zh-cn/docs/concepts/architecture/nodes/#node-controller)

```
Name:               minikube
Roles:              control-plane
Labels:             beta.kubernetes.io/arch=amd64
                    beta.kubernetes.io/os=linux
                    kubernetes.io/arch=amd64
                    kubernetes.io/hostname=minikube
                    kubernetes.io/os=linux
                    minikube.k8s.io/commit=210b148df93a80eb872ecbeb7e35281b3c582c61
                    minikube.k8s.io/name=minikube
                    minikube.k8s.io/primary=true
                    minikube.k8s.io/updated_at=2024_09_12T10_18_37_0700
                    minikube.k8s.io/version=v1.34.0
                    node-role.kubernetes.io/control-plane=
                    node.kubernetes.io/exclude-from-external-load-balancers=
Annotations:        kubeadm.alpha.kubernetes.io/cri-socket: unix:///var/run/cri-dockerd.sock
                    node.alpha.kubernetes.io/ttl: 0
                    volumes.kubernetes.io/controller-managed-attach-detach: true
CreationTimestamp:  Thu, 12 Sep 2024 10:18:34 +0800
Taints:             <none>
Unschedulable:      false
Lease:
  HolderIdentity:  minikube
  AcquireTime:     <unset>
  RenewTime:       Thu, 12 Sep 2024 11:14:05 +0800
Conditions:
  Type             Status  LastHeartbeatTime                 LastTransitionTime                Reason                       Message
  ----             ------  -----------------                 ------------------                ------                       -------
  MemoryPressure   False   Thu, 12 Sep 2024 11:12:20 +0800   Thu, 12 Sep 2024 10:18:32 +0800   KubeletHasSufficientMemory   kubelet has sufficient memory available
  DiskPressure     False   Thu, 12 Sep 2024 11:12:20 +0800   Thu, 12 Sep 2024 10:18:32 +0800   KubeletHasNoDiskPressure     kubelet has no disk pressure
  PIDPressure      False   Thu, 12 Sep 2024 11:12:20 +0800   Thu, 12 Sep 2024 10:18:32 +0800   KubeletHasSufficientPID      kubelet has sufficient PID available
  Ready            True    Thu, 12 Sep 2024 11:12:20 +0800   Thu, 12 Sep 2024 10:18:34 +0800   KubeletReady                 kubelet is posting ready status
Addresses:
  InternalIP:  192.168.49.2
  Hostname:    minikube
Capacity:
  cpu:                12
  ephemeral-storage:  1055762868Ki
  hugepages-1Gi:      0
  hugepages-2Mi:      0
  memory:             16268476Ki
  pods:               110
Allocatable:
  cpu:                12
  ephemeral-storage:  1055762868Ki
  hugepages-1Gi:      0
  hugepages-2Mi:      0
  memory:             16268476Ki
  pods:               110
System Info:
  Machine ID:                 6a11d8d435f44c10bd79509e526dfc15
  System UUID:                6a11d8d435f44c10bd79509e526dfc15
  Boot ID:                    e6fcfe0a-a9e9-45a9-87ce-6d4860caedf1
  Kernel Version:             5.15.153.1-microsoft-standard-WSL2
  OS Image:                   Ubuntu 22.04.4 LTS
  Operating System:           linux
  Architecture:               amd64
  Container Runtime Version:  docker://27.2.0
  Kubelet Version:            v1.31.0
  Kube-Proxy Version:
PodCIDR:                      10.244.0.0/24
PodCIDRs:                     10.244.0.0/24
Non-terminated Pods:          (8 in total)
  Namespace                   Name                                CPU Requests  CPU Limits  Memory Requests  Memory Limits  Age
  ---------                   ----                                ------------  ----------  ---------------  -------------  ---
  default                     nginx-pod                           0 (0%)        0 (0%)      0 (0%)           0 (0%)         38m
  kube-system                 coredns-6f6b679f8f-ddrh5            100m (0%)     0 (0%)      70Mi (0%)        170Mi (1%)     55m
  kube-system                 etcd-minikube                       100m (0%)     0 (0%)      100Mi (0%)       0 (0%)         55m
  kube-system                 kube-apiserver-minikube             250m (2%)     0 (0%)      0 (0%)           0 (0%)         55m
  kube-system                 kube-controller-manager-minikube    200m (1%)     0 (0%)      0 (0%)           0 (0%)         55m
  kube-system                 kube-proxy-hs76f                    0 (0%)        0 (0%)      0 (0%)           0 (0%)         55m
  kube-system                 kube-scheduler-minikube             100m (0%)     0 (0%)      0 (0%)           0 (0%)         55m
  kube-system                 storage-provisioner                 0 (0%)        0 (0%)      0 (0%)           0 (0%)         55m
Allocated resources:
  (Total limits may be over 100 percent, i.e., overcommitted.)
  Resource           Requests    Limits
  --------           --------    ------
  cpu                750m (6%)   0 (0%)
  memory             170Mi (1%)  170Mi (1%)
  ephemeral-storage  0 (0%)      0 (0%)
  hugepages-1Gi      0 (0%)      0 (0%)
  hugepages-2Mi      0 (0%)      0 (0%)
Events:
  Type     Reason                             Age                From             Message
  ----     ------                             ----               ----             -------
  Normal   Starting                           55m                kube-proxy
  Warning  CgroupV1                           55m                kubelet          Cgroup v1 support is in maintenance mode, please migrate to Cgroup v2.
  Normal   NodeHasSufficientMemory            55m (x7 over 55m)  kubelet          Node minikube status is now: NodeHasSufficientMemory
  Normal   NodeHasNoDiskPressure              55m (x7 over 55m)  kubelet          Node minikube status is now: NodeHasNoDiskPressure
  Normal   NodeHasSufficientPID               55m (x7 over 55m)  kubelet          Node minikube status is now: NodeHasSufficientPID
  Normal   NodeAllocatableEnforced            55m                kubelet          Updated Node Allocatable limit across pods
  Warning  PossibleMemoryBackedVolumesOnDisk  55m                kubelet          The tmpfs noswap option is not supported. Memory-backed volumes (e.g. secrets, emptyDirs, etc.) might be swapped to disk and should no longer be considered secure.
  Normal   Starting                           55m                kubelet          Starting kubelet.
  Warning  CgroupV1                           55m                kubelet          Cgroup v1 support is in maintenance mode, please migrate to Cgroup v2.
  Normal   NodeAllocatableEnforced            55m                kubelet          Updated Node Allocatable limit across pods
  Normal   NodeHasSufficientMemory            55m                kubelet          Node minikube status is now: NodeHasSufficientMemory
  Normal   NodeHasNoDiskPressure              55m                kubelet          Node minikube status is now: NodeHasNoDiskPressure
  Normal   NodeHasSufficientPID               55m                kubelet          Node minikube status is now: NodeHasSufficientPID
  Normal   RegisteredNode                     55m                node-controller  Node minikube event: Registered Node minikube in Controller
```