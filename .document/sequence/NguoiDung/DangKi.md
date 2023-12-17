```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang đăng kí
participant ui1 as Trang đăng nhập
participant manage as Quản lí tài khoản
participant db as Tài khoản
autonumber

user->>+ui: Yêu cầu đăng kí
activate user
activate ui
ui->>+manage: Xử lí đăng kí
activate manage
activate ui
manage->>db: Truy xuất dữ liệu tài khoản
db-->manage: Trả về kết quả
manage-->>ui: Trả về kết quả
deactivate manage
ui->>ui1:Hiển thị giao diện
ui1-->>user:Hiển thị giao diện
deactivate ui
deactivate user


```
