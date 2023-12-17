```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang Đọc Sách
participant ui1 as Form ghi chú
participant manage as Quản lí ghi chú sách
participant db as Ghi Chú Sách
autonumber

user->>+ui: Yêu cầu thêm ghi chú
ui->>+ui1: Hiển thị giao diện
user->>+ui1: Thêm nội dung ghi chú
ui1->>+manage: Xử lí yêu cầu thêm ghi chú
manage->>+db: Tiến hành thêm ghi chú
db-->>-manage:Trả về kết quả
alt Thành công
  manage-->>ui:Trả về thông báo thêm thành công
else Thất bại
  manage-->>ui:Trả về thông báo thêm thất bại
end
ui->>+ui: Cập nhật giao diện
ui-->>-user: Hiển thị kết quả
```
