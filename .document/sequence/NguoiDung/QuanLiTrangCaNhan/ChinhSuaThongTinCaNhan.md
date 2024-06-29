```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang Cá Nhân
participant manage as Quản lí tài khoản
participant db as Tài Khoản
autonumber

user->>+ui: Điền thông tin cần cập nhật
activate ui
user->>+ui: Yêu cầu cập nhật
ui->>+manage: Xử lí yêu cầu cập nhật
activate manage
manage->>+db: Tiến hành cập nhật
db-->>-manage:Trả về kết quả
manage-->>ui:Trả về kết quả cập nhật thông tin thành công
deactivate manage
ui->>+ui: Cập nhật giao diện
ui-->>-user: Hiển thị thông báo
deactivate ui
```
