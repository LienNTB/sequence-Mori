```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang đăng nhập
participant ui1 as Trang chủ
participant api as Google API
participant manage as Quản lí tài khoản
participant db as Tài khoản
autonumber

user->>+ui: Yêu cầu đăng nhập
activate user
activate ui
ui->>+manage: Xử lí đăng nhập
activate manage
activate ui
manage->>db: Truy xuất dữ liệu tài khoản
db-->manage: Trả về kết quả

alt Đăng nhập Google
manage->>api: Xử lí đăng nhập bằng Google
activate api
api-->>db: Trả về kết quả
deactivate api
db-->>manage: Trả về kết quả
end
manage-->>ui: Trả về kết quả
deactivate manage
ui->>ui1:Hiển thị giao diện
ui1-->>user:Hiển thị giao diện
deactivate ui
deactivate user


```
