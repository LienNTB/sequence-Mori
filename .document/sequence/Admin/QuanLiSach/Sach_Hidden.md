```mermaid
sequenceDiagram
actor user as Admin
participant ui as Trang quản lí sách
participant manage as Quản lí sách
participant db as Sách
autonumber


user->>+ui: Yêu cầu ẩn sách
activate user
activate ui
ui->>+manage: Xử lí ẩn sách
activate manage
manage->>+db: Xử lí dữ liệu sách
db->>-manage:Trả về kết quả
alt success
  manage-->>ui:Trả về thông báo ẩn sách thành công
else error
  manage-->>-ui:Trả về thông báo lỗi cụ thể khi ẩn sách 
end
ui->>+ui: Cập nhật giao diện
ui-->>-user: Hiển thị kết quả
deactivate ui
deactivate user
```
