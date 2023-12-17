```mermaid
sequenceDiagram
actor user as Admin
participant ui as Trang quản lí sách
participant ui1 as Trang sửa sách
participant manage as Quản lí sách
participant db as Sách
participant azure as Azure
autonumber


user->>+ui: Yêu cầu sửa sách
activate user
activate ui
ui->>+ui1: Hiển thị giao diện
user->>+ui1: Chon file và gửi yêu cầu upload Image
activate ui1
activate azure
ui1->>+azure: Xử lí yêu cầu upload Image
azure->>+ui1: Trả về kết quả upload
deactivate azure

alt success
  ui1->>+manage: Xử lí yêu cầu sửa sách
  activate manage
  manage->>+db: Xử lí dữ liệu sách
  db->>-manage:Trả về kết quả
  alt success
    manage-->>ui:Trả về thông báo sửa sách thành công
  else error
    manage-->>-ui:Trả về thông báo lỗi cụ thể khi sửa sách
  end
else error
  ui1->>-ui: Trả về thông báo lỗi cụ thể khi upload Image
end
deactivate ui1
ui->>+ui: Cập nhật giao diện
ui-->>-user: Hiển thị kết quả
deactivate ui
deactivate user
```
