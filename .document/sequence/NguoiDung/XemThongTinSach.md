```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang Chủ
participant ui2 as Trang Chi Tiết Sách
participant manage as Quản lí sách
participant db as Sách
autonumber

user->>+ui: Yêu cầu xem thông tin sách
ui->>+manage: Xử lí sách theo id
manage->>+db: Truy xuất dữ liệu sách theo id

db-->>-manage:Trả về kết quả sách
manage-->>-ui2:Trả về kết quả
ui2->>+ui2: Cập nhật giao diện
ui2-->>-user: Hiển thị kết quả
```
