```mermaid
sequenceDiagram
actor user as Admin
participant ui as Trang quản lí tài khoản
participant ui1 as Trang sửa tài khoản
participant manage as Quản lí tài khoản
participant db as Tài khoản
autonumber


user->>+ui: Yêu cầu sửa tài khoản
activate user
activate ui
ui->>+ui1: Hiển thị giao diện
user->>+ui1: Nhập thông tin tài khoản
ui1->>+manage: Xử lí yêu cầu sửa tài khoản
activate manage
manage->>+db: Xử lí dữ liệu tài khoản
db->>-manage:Trả về kết quả
alt success
  manage-->>ui:Trả về thông báo sửa tài khoản thành công
else error
  manage-->>-ui:Trả về thông báo lỗi cụ thể khi sửa tài khoản
end
ui->>+ui: Cập nhật giao diện
ui-->>-user: Hiển thị kết quả
deactivate ui
deactivate user
```
