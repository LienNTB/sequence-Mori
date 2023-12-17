```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang Chủ
participant manage as Quản lí sách
participant db as Sách

user->>+ui: Yêu cầu tìm kiếm
ui->>+manage: Xử lí tìm kiếm sách theo từ khóa
manage->>+db: Truy xuất dữ liệu

db-->>-manage:Trả về kết quả
manage-->>-ui:Trả về kết quả
ui->>+ui: Cập nhật giao diện
ui-->>-user: Hiển thị kết quả tìm kiếm
```
