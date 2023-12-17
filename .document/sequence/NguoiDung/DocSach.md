```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang Chi Tiết Sách
participant ui2 as Trang Đọc Sách
participant manage as Quản lí sách
participant db as Sách
autonumber

user->>+ui: Yêu cầu đọc sách
ui->>+manage: Xử lí đọc sách
manage->>+db: Truy xuất dữ liệu file epub

db->>-manage:Trả về kết quả
manage->>-ui2:Trả về kết quả
ui2->>+ui2: Cập nhật giao diện
ui2->>-user: Hiển thị kết quả
```
