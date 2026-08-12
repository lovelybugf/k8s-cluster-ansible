# Kubernetes Cluster Administration & Operations (Ansible GitOps)

Repository kịch bản Ansible tự động hóa vận hành, bảo trì và chuẩn hóa cụm Kubernetes 2 Nodes (`k8s-master` & `k8s-worker`) thông qua **AWX**.

## 📁 Cấu trúc dự án
*   **`playbooks/`**: Thư mục chứa các kịch bản chạy tác vụ cụ thể.
    *   `os_update.yml`: Cập nhật OS, nâng cấp phần mềm, tự động khởi động lại an toàn.
    *   `disk_cleanup.yml`: Dọn dẹp logs, giải phóng bộ nhớ đệm container.
    *   `etcd_backup.yml`: Tự động sao lưu cơ sở dữ liệu etcd (chỉ chạy trên Master).
    *   `k8s_cert_renew.yml`: Gia hạn chứng chỉ TLS nội bộ của cụm K8s.
*   **`group_vars/`**: Định nghĩa biến dùng chung.

## 🚀 Cách sử dụng trên AWX
1.  Đẩy toàn bộ thư mục này lên GitHub cá nhân của bạn.
2.  Tạo **Project** trên AWX trỏ về Repo GitHub đó.
3.  Tạo các **Job Templates** và liên kết với Inventory + SSH Machine Credentials để chạy.
