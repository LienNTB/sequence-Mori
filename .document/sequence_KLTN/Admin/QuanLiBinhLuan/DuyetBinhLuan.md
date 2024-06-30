```mermaid
sequenceDiagram
actor user as Admin
participant ui as Trang quản lí bình luận
participant manage as Quản lí bình luận
participant db as Bình luận
autonumber


user->>+ui: Yêu cầu duyệt bình luận
activate user
activate ui
ui->>+manage: Xử lí duyệt bình luận
activate manage
manage->>+db: Xử lí dữ liệu bình luận
db->>-manage:Trả về kết quả
alt success
  manage-->>ui:Trả về thông báo thành công
else error
  manage-->>-ui:Trả về thông báo thất bại
end
ui->>+ui: Cập nhật giao diện
ui-->>-user: Hiển thị kết quả
deactivate ui
deactivate user
```
