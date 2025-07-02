# 在 Kubernetes 上部署 WordPress

这是一个用于在 Kubernetes (Minikube) 环境中部署一个完整 WordPress 网站的毕业项目。

该项目包含一个 WordPress 前端和一个 MySQL 后端数据库，并综合运用了 Kubernetes 的多项核心技术。

## 项目特点

* **Deployment**: 使用 Deployment 来管理 WordPress 和 MySQL 的 Pod，确保应用的高可用性。
* **Service**: 使用 Service (ClusterIP 和 NodePort) 来实现服务发现和外部访问。
* **PersistentVolumeClaim (PVC)**: 为 MySQL 数据库和 WordPress 的用户上传内容提供了持久化存储，确保数据在 Pod 重启后不丢失。
* **Secret**: 使用 Secret 来安全地管理 MySQL 的数据库密码。

## 如何部署

1.  **前提**: 确保您拥有一个可以工作的 Kubernetes 集群（例如 Minikube）和 `kubectl` 命令行工具。
2.  **部署 MySQL**:
    ```bash
    kubectl apply -f mysql-deployment.yaml
    ```
3.  **部署 WordPress**:
    ```bash
    kubectl apply -f wordpress-deployment.yaml
    ```
4.  **访问网站**:
    使用以下命令获取访问 URL，然后在浏览器中打开它。
    ```bash
    minikube service wordpress-service --url
    ```
