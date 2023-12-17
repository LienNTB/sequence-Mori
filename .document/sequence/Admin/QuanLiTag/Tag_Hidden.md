```mermaid
sequenceDiagram
actor user as Admin
participant ui as Trang quản lí tag
participant manage as Quản lí tag
participant db as Tag
autonumber


user->>+ui: Yêu cầu ẩn tag
activate user
activate ui
ui->>+manage: Xử lí ẩn tag
activate manage
manage->>+db: Xử lí dữ liệu tag
db->>-manage:Trả về kết quả
alt success
  manage-->>ui:Trả về thông báo ẩn tag thành công
else error
  manage-->>-ui:Trả về thông báo lỗi cụ thể khi ẩn tag
end
ui->>+ui: Cập nhật giao diện
ui-->>-user: Hiển thị kết quả
deactivate ui
deactivate user
```
