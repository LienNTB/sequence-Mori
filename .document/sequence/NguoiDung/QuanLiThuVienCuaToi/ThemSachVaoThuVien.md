```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang Chi Tiết Sách
participant manage as Quản lí sách
participant db as Sách
autonumber

user->>+ui: Yêu cầu thêm sách vào thư viện
activate user
activate ui
ui->>+manage: Xử lí thêm sách
activate manage
manage->>+db: Xử lí dữ liệu sách
db->>-manage:Trả về kết quả
alt Chưa đăng kí gói cước
  manage-->>-ui:Trả về kết quả cần đăng kí gói cước
else Đã đăng kí gói cước
  manage-->>-ui:Trả về kết quả thêm vào thư viện thành công
end
ui->>+ui: Cập nhật thông báo
ui-->>-user: Hiển thị kết quả
deactivate ui
deactivate user

```
