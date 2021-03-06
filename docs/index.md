# 项目介绍

KubeOperator 是一个开源的轻量级 Kubernetes 发行版，专注于帮助企业规划、部署和运营生产级别的 Kubernetes 集群。

KubeOperator 提供可视化的 Web UI，支持离线环境，支持物理机、VMware 和 OpenStack 等 IaaS 平台，支持 x86 和 ARM64 架构，支持 GPU，内置应用商店，已通过 CNCF 的 Kubernetes 软件一致性认证。

KubeOperator 使用 Terraform 在 IaaS 平台上自动创建主机（用户也可以自行准备主机，比如物理机或者虚机），通过 Ansible 完成自动化部署和变更操作，支持 Kubernetes 集群 从 Day 0 规划，到 Day 1 部署，到 Day 2 运营的全生命周期管理。

## 整体架构

![Architecture](https://kubeoperator.io/images/screenshot/ko-framework.svg)

## 界面展示

![Web UI](https://kubeoperator.io/images/screenshot/05.jpg)

## 视频演示

[视频演示](https://www.bilibili.com/video/BV1jT4y1L7Ur/)

## 技术优势

-  简单易用: 提供可视化的 Web UI，极大降低 Kubernetes 部署和管理门槛，内置 [Webkubectl](https://github.com/KubeOperator/webkubectl)
-  按需创建: 调用云平台 API，一键快速创建和部署 Kubernetes 集群
-  按需伸缩: 快速伸缩 Kubernetes 集群，优化资源使用效率
-  按需修补: 快速升级和修补 Kubernetes 集群，并与社区最新版本同步，保证安全性
-  离线部署: 支持完全离线下的 Kubernetes 集群部署
-  自我修复: 通过重建故障节点确保集群可用性
-  全栈监控: 提供从Pod、Node到集群的事件、监控、告警、和日志方案
-  Multi-AZ 支持: 将 Master 节点分布在不同的故障域上确保集群高可用
-  应用商店: 内置 [KubeApps](https://github.com/kubeapps/kubeapps) 应用商店
-  GPU 支持: 支持 GPU 节点，助力运行深度学习等应用

## 功能列表

<table>
    <tr>
        <td rowspan="16">Day 0 规划</td>
        </td>
        <td rowspan="2">集群模式
        </td>
        <td>1 个 Master 节点 n 个 Worker 节点模式：适合开发测试用途
        </td>       
    </tr>
    <tr>
        <td>3 个 Master 节点 n 个 Worker 节点模式：适合生产用途
        </td>
    </tr>    
    <tr>
        <td rowspan="4">计算方案
        </td>
        <td>独立主机：支持自行准备的虚机、公有云主机和物理机
        </td>  
    </tr>    
    <tr>
        <td>vSphere 平台：支持自动创建主机（使用 Terraform）
        </td>
    </tr>
    <tr>
        <td>Openstack 平台：支持自动创建主机 （使用 Terraform）
        </td>
    </tr>
    <tr>
        <td>支持 x86 和 Arm64 CPU 架构
        </td>
    </tr>
    <tr>
        <td rowspan="3">存储方案
        </td>
        <td>独立主机：支持 NFS / Ceph RBD / Local Volume
        </td>
    </tr>
    <tr>
        <td>vSphere 平台：支持 vSphere Datastore （vSAN 及 vSphere 兼容的集中存储）
        </td>
    </tr> 
     <tr>
        <td>Openstack 平台：支持 Openstack Cinder （Ceph 及 Cinder 兼容的集中存储）
        </td>
    </tr>
    <tr>
        <td rowspan="4">网络方案
        </td>
        <td>支持 Flannel / Calico 网络插件
        </td>
    </tr>
    <tr>
        <td>支持通过 F5 Big IP 对外暴露服务
        </td>
    </tr> 
    <tr>
        <td>支持 Traefik / ingress-nginx
        </td>
    </tr>    
    <tr>
        <td>支持 CoreDNS
        </td>
    </tr>
    <tr>
        <td>GPU 方案
        </td>
        <td>支持 NVIDIA GPU
        </td>
    </tr> 
    <tr>
        <td>操作系统
        </td>
        <td>支持 RHEL/CentOS 7.4 以上版本
        </td>
    </tr>  
    <tr>
        <td>容器运行时
        </td>
        <td>支持 Docker / containerd
        </td>
    </tr>     
    <tr>
        <td rowspan="3">Day 1 部署
        </td>
        <td rowspan="3">部署
        </td>  
        <td>提供离线环境下的完整安装包
        </td>         
    </tr>
     <tr>
        <td>支持可视化方式展示部署过程
        </td>
    </tr>
     <tr>
        <td>支持一键自动化部署（使用 Ansible）
        </td>
    </tr> 
    <tr>
        <td rowspan="21">Day 2 运营
        </td>
        <td rowspan="9">管理
        </td>  
        <td>支持以项目为核心的分级授权管理
        </td>         
    </tr>
    <tr>
         <td>支持系统管理员、项目管理员和只读用户等三种角色
        </td>
    </tr> 
    <tr>
         <td>支持对接 LDAP/AD
        </td>
    </tr>    
    <tr>
         <td>对外开放 REST API
        </td>
    </tr>    
    <tr>
         <td>可通过应用商店安装 K8s Dashboard 管理应用
        </td>
    </tr>     
     <tr>
         <td>可通过应用商店安装 Weave Scope 管理应用
        </td>
    </tr>  
    <tr>
         <td>提供 Web Kubectl 界面
        </td>
    </tr> 
    <tr>
         <td>内置 Helm 
        </td>
    </tr>   
    <tr>
         <td>支持更新证书
        </td>
    </tr>     
    <tr>
        <td rowspan="4">可观察性
        </td>
         <td>内置 Promethus，支持对集群、节点、Pod、Container的全方位监控和告警
        </td>
    </tr>
     <tr>
        <td>内置 Loki 日志方案
        </td>
    </tr> 
    <tr>
        <td>内置 Grafana 作为监控和日志展示
        </td>
    </tr> 
    <tr>
        <td>支持消息中心，通过钉钉、微信通知各种集群异常事件；
        </td>
    </tr>      
    <tr>
        <td>升级
        </td>
         <td>支持集群升级
        </td>
    </tr> 
    <tr>
        <td>伸缩
        </td>
         <td>支持增加或者减少 Worker 节点
        </td>
    </tr>
    <tr>
        <td>备份
        </td>
         <td>支持 etcd 定期备份
        </td>
    </tr>  
    <tr>
        <td  rowspan="2">安全合规
        </td>
         <td>支持集群健康评分
        </td>
    </tr>   
    <tr>
        <td>支持 CSI 安全扫描
        </td>
    </tr>    
    <tr>
        <td rowspan="2">应用商店
        </td>
         <td>提供 GitLab、Jenkins、Harbor、Argo CD 等 CI/CD 工具
        </td>
    </tr> 
    <tr>
        <td>提供深度学习AI 应用，比如 TensorFlow
        </td>
    </tr>    
 </table>

## 支持组件

!!! info "核心"
    * [kubernetes](https://github.com/kubernetes/kubernetes) v1.18.4
    * [etcd](https://github.com/coreos/etcd) v3.4.9
    * [docker](https://www.docker.com/) v19.03.9
    * [containerd](https://containerd.io/) v1.3.6
  
!!! info "网络"
    * [calico](https://github.com/projectcalico/calico) v3.14.1
    * [flanneld](https://github.com/coreos/flannel) v0.12.0

!!! info "应用"
    * [coredns](https://github.com/coredns/coredns) v1.6.7
    * [helm](https://github.com/helm/helm) v3.2.4
    * [traefik](https://github.com/containous/traefik) v2.2.1
    * [ingress-nginx](https://github.com/kubernetes/ingress-nginx) v0.32.0
    * [node-problem-detector](https://github.com/kubernetes/node-problem-detector) v0.8.1
    * [metrics-server](https://github.com/kubernetes-sigs/metrics-server) v0.3.6
    * [nfs-provisioner](https://github.com/kubernetes-incubator/external-storage) v3.1.0-k8s1.11
    * [rook-ceph](https://github.com/rook/rook) v1.3.6
    * [rbd-provisioner](https://github.com/kubernetes-incubator/external-storage) v2.1.1-k8s1.11

## 企业版试用

- [申请企业版试用](https://jinshuju.net/f/qc6g44)

> 注: 企业版支持离线安装，申请通过后会提供高速下载链接

## 更多阅读

- [干货分享丨KubeOperator如何助力企业运营生产级别的Kubernetes集群？](https://blog.fit2cloud.com/?p=1255)
- [PPT 介绍](https://kubeoperator.io/download/KubeOperator_Intro.pdf)
