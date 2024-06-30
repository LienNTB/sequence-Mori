```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang thêm bài đăng mới
participant manage as Quản lí bài đăng
participant db as Bài đăng
autonumber

user->>+ui: Yêu cầu thêm bài đăng
activate user
activate ui
ui->>+manage: Xử lí thêm bài đăng
activate manage
manage->>+db: Xử lí dữ liệu bài đăng
alt Thành công
db->>manage:Trả về kết quả thành công
manage-->>-ui:Trả về kết quả
ui->>+ui: Cập nhật thông báo
ui-->>-user: Hiển thị thông báo thành công
else Thất bại
db->>-manage:Trả về kết quả nhập thiếu thông tin
manage-->>-ui:Trả về kết quả
ui->>+ui: Cập nhật thông báo
ui-->>-user: Hiển thị thông báo lỗi
end
deactivate ui
deactivate user

```
