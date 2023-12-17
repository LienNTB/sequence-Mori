```mermaid
sequenceDiagram
actor user as Admin
participant ui as Trang quản lí sách
participant ui1 as Trang thêm sách
participant manage as Quản lí sách
participant db as Sách
autonumber


user->>+ui: Yêu cầu thêm sách
activate user
activate ui
ui->>+ui1: Hiển thị giao diện
user->>+ui1: Nhập thông tin sách
ui1->>+manage: Xử lí yêu cầu thêm sách
activate manage
manage->>+db: Xử lí dữ liệu sách
db->>-manage:Trả về kết quả
alt success
  manage-->>ui:Trả về thông báo thêm sách thành công
else error
  manage-->>-ui:Trả về thông báo lỗi cụ thể khi thêm sách
end
ui->>+ui: Cập nhật giao diện
ui-->>-user: Hiển thị kết quả
deactivate ui
deactivate user
```
