```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang cá nhân
participant ui1 as Mục thư viện của tôi
participant manage as Quản lí thư viện
participant db as Sách
autonumber

user->>+ui: Yêu cầu Chọn giao diện
activate user
activate ui
ui->>+ui1: Hiển thị giao diện
deactivate ui
ui1-->>-user: Trả về kết quả
user->>+ui1: Yêu cầu xóa sách khỏi thư viện
ui1->>+manage:Xử lí xóa sách
manage->>+db: Truy xuất dữ liệu
db-->>-manage: Trả về kết quả
manage-->-ui1: Trả về kết quả
ui1-->>ui1: Cập nhật giao diện
ui1-->>-user: Hiển thị thông báo
deactivate user
```
