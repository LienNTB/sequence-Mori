```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang Chi Tiết Sách
participant manage as Quản lí sách
participant db as Sách
autonumber

user->>+ui: Yêu cầu xem thông tin sách
ui->>+manage: Xử lí sách theo id
manage->>+db: Truy xuất dữ liệu sách theo id

db-->>-manage:Trả về kết quả review sách
manage-->>-ui:Trả về kết quả
ui->>+ui: Cập nhật giao diện
ui-->>-user: Hiển thị kết quả
```
