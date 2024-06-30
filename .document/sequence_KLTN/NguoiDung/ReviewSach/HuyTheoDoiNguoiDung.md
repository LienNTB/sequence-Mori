```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang cá nhân người dùng
participant manage as Quản lí tài khoản
participant db as Tài khoản
autonumber

user->>+ui: Yêu cầu hủy theo dõi người dùng
activate user
activate ui
ui->>+manage: Xử lí hủy theo dõi người dùng
activate manage
manage->>+db: Xử lí dữ liệu tài khoản
alt Đã đăng nhập
db->>manage:Trả về kết quả thành công
manage-->>-ui:Trả về kết quả
ui->>+ui: Cập nhật thông báo
ui-->>-user: Hiển thị thông báo thành công
else Chưa đăng nhập
db->>-manage:Trả về kết quả thất bại
manage-->>-ui:Trả về kết quả
ui->>+ui: Cập nhật thông báo
ui-->>-user: Hiển thị thông báo lỗi
end
deactivate ui
deactivate user

```
