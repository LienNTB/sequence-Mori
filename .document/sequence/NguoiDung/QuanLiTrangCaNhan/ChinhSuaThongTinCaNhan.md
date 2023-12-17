```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang Cá Nhân
participant manage as Quản lí tài khoản
participant db as Tài Khoản
autonumber

user->>+ui: Điền thông tin cần cập nhật
user->>+ui: Yêu cầu cập nhật
ui1->>+manage: Xử lí yêu cầu cập nhật
manage->>+db: Tiến hành cập nhật
db-->>-manage:Trả về kết quả
alt Thành công
  manage-->>ui:Trả về thông báo cập nhật thành công
else Thất bại
  manage-->>ui:Trả về thông báo cập nhật thất bại
end
ui->>+ui: Cập nhật giao diện
ui-->>-user: Hiển thị kết quả
```
