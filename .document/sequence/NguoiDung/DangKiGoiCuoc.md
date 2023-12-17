```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang đăng kí gói cước
participant api as Cổng thanh toán Momo
participant manage as Quản lí gói cước
participant db as Gói cước
autonumber

user->>+ui: Yêu cầu đăng kí gói cước
activate user
activate ui
ui->>+manage: Xử lí đăng kí gói cước
manage->>+api: Thực hiện thanh toán
activate api
api-->>-db:Lưu kết quả thanh toán
activate db
deactivate api
db-->>manage:Trả về kết quả
deactivate db
manage-->>-ui:Trả về kết quả
ui-->>ui: Cập nhật giao diện
ui-->>user: Hiển thị kết quả
deactivate ui
deactivate user
```
