```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang Chi Tiết Sách
participant manage as Quản lí sách
participant db as Review Sách
autonumber

user->>+ui: Yêu cầu xóa review sách
activate user
activate ui
ui->>+manage: Xử lí xóa review sách
activate manage
manage->>+db: Xử lí dữ liệu review sách
db->>-manage:Trả về kết quả
manage-->>-ui:Trả về kết quả
ui->>+ui: Cập nhật thông báo
ui-->>-user: Hiển thị kết quả
deactivate ui
deactivate user

```
