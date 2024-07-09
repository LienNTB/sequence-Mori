```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Form đổi mật khẩu
participant manage as Quản lí tài khoản
participant db as Tài khoản
autonumber

user->>+ui: Yêu cầu đổi mật khẩu
activate user
activate ui
ui->>+manage: Xử lí đổi mật khẩu
activate manage
manage->>+db: Xử lí dữ liệu mật khẩu
alt Thành công
db->>manage:Trả về kết quả thành công
manage-->>-ui:Trả về kết quả
ui->>+ui: Cập nhật thông báo
ui-->>-user: Hiển thị thông báo thành công
else Thất bại
db->>-manage:Trả về thông báo thất bại
manage-->>-ui:Trả về kết quả
ui->>+ui: Cập nhật thông báo
ui-->>-user: Hiển thị thông báo lỗi
end
deactivate ui
deactivate user

```
