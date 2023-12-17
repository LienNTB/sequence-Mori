```mermaid
sequenceDiagram
actor user as Admin
participant ui as Trang quản lí danh mục sách
participant ui1 as Trang sửa danh mục sách
participant manage as Quản lí danh mục sách
participant db as Danh mục sách
autonumber


user->>+ui: Yêu cầu sửa danh mục sách
activate user
activate ui
ui->>+ui1: Hiển thị giao diện
user->>+ui1: Nhập thông tin danh mục sách
ui1->>+manage: Xử lí yêu cầu sửa danh mục sách
activate manage
manage->>+db: Xử lí dữ liệu danh mục sách
db->>-manage:Trả về kết quả
alt success
  manage-->>ui:Trả về thông báo sửa danh mục sách thành công
else error
  manage-->>-ui:Trả về thông báo lỗi cụ thể khi sửa danh mục sách
end
ui->>+ui: Cập nhật giao diện
ui-->>-user: Hiển thị kết quả
deactivate ui
deactivate user
```
