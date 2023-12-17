```mermaid
sequenceDiagram
actor user as Admin
participant ui as Trang quản lí tài khoản
participant manage as Quản lí tài khoản
participant db as Tài khoản
autonumber


user->>+ui: Yêu cầu khóa tài khoản
activate user
activate ui
ui->>+manage: Xử lí khóa tài khoản
activate manage
manage->>+db: Xử lí dữ liệu tài khoản
db->>-manage:Trả về kết quả
alt success
  manage-->>ui:Trả về thông báo khóa tài khoản thành công
else error
  manage-->>-ui:Trả về thông báo lỗi cụ thể khi khóa tài khoản 
end
ui->>+ui: Cập nhật giao diện
ui-->>-user: Hiển thị kết quả
deactivate ui
deactivate user
```
