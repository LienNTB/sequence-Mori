```mermaid
sequenceDiagram
actor user as Admin
participant ui as Trang quản lí tag
participant ui1 as Trang sửa tag
participant manage as Quản lí tag
participant db as Tag
autonumber


user->>+ui: Yêu cầu sửa tag
activate user
activate ui
ui->>+ui1: Hiển thị giao diện
user->>+ui1: Nhập thông tin tag
ui1->>+manage: Xử lí yêu cầu sửa tag
activate manage
manage->>+db: Xử lí dữ liệu tag
db->>-manage:Trả về kết quả
alt success
  manage-->>ui:Trả về thông báo sửa tag thành công
else error
  manage-->>-ui:Trả về thông báo lỗi cụ thể khi sửa tag
end
ui->>+ui: Cập nhật giao diện
ui-->>-user: Hiển thị kết quả
deactivate ui
deactivate user
```
