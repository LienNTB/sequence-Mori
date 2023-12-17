```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang Chi Tiết Sách
participant manage as Quản lí sách
participant db as Sách
autonumber

user->>+ui: Yêu cầu nghe sách nói
ui->>+manage: Xử lí audio sách nói
manage->>+db: Truy xuất dữ liệu

db->>-manage:Trả về kết quả
manage->>-ui:Trả về kết quả
ui->>+ui: Cập nhật giao diện
ui->>-user: Hiển thị audio sách nói
```
