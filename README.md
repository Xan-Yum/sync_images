# 经GitHub将kubernetes镜像推送到阿里云

# 背景



在安装kubernetes时会出现无法访问镜像站的情况，通过GitHub将kubernetes镜像推送到阿里云之后，即可使用阿里云地址引用所需镜像，当前在陆续同步。



# 代码仓库

https://github.com/Xan-Yum/sync_images
若有需要自行研究 后续更新会在仓库更新


# 目前有如下镜像仓库，后续会陆续增加

```yaml
  docker.elastic.co:
    - elasticsearch/elasticsearch
    - kibana/kibana
    - logstash/logstash
    - beats/filebeat
    - beats/heartbeat
    - beats/packetbeat
    - beats/auditbeat
    - beats/journalbeat
    - beats/metricbeat
    - apm/apm-server
    - app-search/app-search
  quay.io:
    - coreos/flannel
    - ceph/ceph
    - cephcsi/cephcsi
    - csiaddons/k8s-sidecar
    - csiaddons/volumereplication-operator
    - prometheus/prometheus
    - prometheus/alertmanager
    - prometheus/pushgateway
    - prometheus/blackbox-exporter
    - prometheus/node-exporter
    - prometheus-operator/prometheus-config-reloader
    - prometheus-operator/prometheus-operator
    - brancz/kube-rbac-proxy
    - cilium/cilium
    - cilium/operator-generic
    - thanos/thanos
    - cilium/certgen
    - cilium/hubble-relay
    - cilium/hubble-ui-backend
    - cilium/hubble-ui
    - cilium/cilium-etcd-operator
    - cilium/operator
    - cilium/startup-script
    - cilium/clustermesh-apiserver
    - coreos/etcd
  k8s.gcr.io:
    - dns/k8s-dns-node-cache
    - metrics-server/metrics-server
    - kube-state-metrics/kube-state-metrics
    - prometheus-adapter/prometheus-adapter
    - sig-storage/nfs-subdir-external-provisioner
    - sig-storage/csi-node-driver-registrar
    - sig-storage/csi-provisioner
    - sig-storage/csi-resizer
    - sig-storage/csi-snapshotter
    - sig-storage/csi-attacher
    - sig-storage/nfsplugin
  registry.k8s.io:
    - pause
    - etcd
    - conformance
    - kube-proxy
    - kube-apiserver
    - kube-scheduler
    - kube-controller-manager
    - coredns/coredns
    - ingress-nginx/controller
    - ingress-nginx/controller-chroot
    - ingress-nginx/kube-webhook-certgen
  gcr.io:
    - kaniko-project/executor
    - google-samples/xtrabackup
  docker.io:
    - calico/node
    - calico/typha
    - calico/cni
    - calico/node
    - calico/kube-controllers
    - calico/pod2daemon-flexvol
```

# 使用方式

```bash
docker.elastic.co/kibana/{image_name}  ==>  registry.cn-hangzhou.aliyuncs.com/waluna/{image_name}
quay.io/csiaddons/{image_name}  ==>  registry.cn-hangzhou.aliyuncs.com/waluna/{image_name}
k8s.gcr.io/{image_name}  ==>  registry.cn-hangzhou.aliyuncs.com/waluna/{image_name}
....
```

# 拉去镜像
```bash
docker pull registry.cn-hangzhou.aliyuncs.com/waluna/kube-scheduler:[镜像版本号]
```

# 声明
此仓库基于  https://github.com/lework/sync_image  和 https://github.com/cby-chen/sys_images 修改得来


> **关于**
>
> https://blog.waluna.top/
>
> **CSDN、GitHub、知乎、开源中国、思否、掘金、简书、华为云、阿里云、腾讯云、哔哩哔哩、今日头条、新浪微博、个人博客**
>
> **全网可搜《阿贤Linux》**
>
> **文章主要发布于个人博客**
