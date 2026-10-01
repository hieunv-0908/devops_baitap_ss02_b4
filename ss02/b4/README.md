# Bài Tập 4: Cấu Hình Tường Lửa Bảo Vệ Máy Chủ (UFW & Cloud Firewall)

## 📌 Tổng Quan & Mục Tiêu
Bài tập này triển khai chiến lược **Bảo vệ nhiều lớp (Defense in Depth)** cho máy chủ Ubuntu nhằm thu hẹp bề mặt tấn công (Attack Surface). Hệ thống chỉ mở đúng các cổng dịch vụ cần thiết (**SSH - 22/tcp** để quản trị và **HTTP - 80/tcp** cho Web Server), tất cả các cổng còn lại đều bị chặn mặc định.

---

## 🛠️ Triển Khai Thực Hiện

### 1. Lớp 1: Cấu hình UFW (Uncomplicated Firewall) trong OS

Thao tác trực tiếp trên máy chủ Ubuntu để cấu hình tường lửa tầng ứng dụng/OS:

#### Bước 1: Thiêt lập quy tắc mặc định (Default Policies)
Thiết lập nguyên tắc "Chặt chẽ đầu vào, cởi mở đầu ra":
```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing