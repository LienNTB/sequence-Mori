```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang sửa bài đăng
participant manage as Quản lí bài đăng
participant db as Bài đăng
autonumber

user->>+ui: Yêu cầu sửa bài đăng
activate user
activate ui
ui->>+manage: Xử lí sửa bài đăng
activate manage
manage->>+db: Xử lí dữ liệu bài đăng
db->>-manage:Trả về kết quả thành công
manage-->>-ui:Trả về kết quả
ui->>+ui: Cập nhật thông báo
ui-->>-user: Hiển thị thông báo
deactivate ui
deactivate user

```
