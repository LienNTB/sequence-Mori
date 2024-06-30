```mermaid
sequenceDiagram
actor user as Admin
participant ui as Giao diện quản lí voucher
participant manage as Quản lí voucher
participant db as Voucher
autonumber


user->>+ui: Yêu cầu xóa voucher
activate user
activate ui
ui->>+manage: Xử lí xóa voucher
activate manage
manage->>+db: Xử lí dữ liệu voucher
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
