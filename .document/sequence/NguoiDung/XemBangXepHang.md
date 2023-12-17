```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang Bảng Xếp Hạng
participant manage as Quản lí sách
participant db as Xếp Hạng Sách
autonumber

user->>+ui: Yêu cầu hiển thị dữ liệu
ui->>+manage: Xử lí hiển thị xếp hạng sách
manage->>+db: Truy xuất dữ liệu xếp hạng sách theo ngày

db-->>-manage:Trả về kết quả
manage-->>-ui:Trả về kết quả
ui->>+ui: Cập nhật giao diện
ui-->>-user: Hiển thị kết quả
```
