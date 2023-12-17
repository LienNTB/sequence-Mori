```mermaid
sequenceDiagram
actor user as Admin
participant ui as Trang quản lí sách
participant ui1 as Trang sửa sách
participant chap as Chapter
participant book as Sách
participant azure as Azure
autonumber


user->>+ui: Yêu cầu sửa sách
activate user
activate ui
ui->>+ui1: Hiển thị giao diện
user->>+ui1: Chon file và gửi yêu cầu upload Audio
activate ui1
activate azure
ui1->>+azure: Xử lí yêu cầu upload Audio
azure->>+ui1: Trả về kết quả upload
deactivate azure

alt success
  activate chap
  ui1->>+chap: Xử lí yêu cầu thêm chapter
  
  alt success
    chap->>book: Thêm chapter vào sách
    activate book
    book->>ui1: Trả về kết quả thành công
  deactivate book

  else error
    chap->>ui1: Trả về lỗi khi thêm chapter
  end
  deactivate chap
  ui1->>ui: Trả về thông báo upload chapter thành công

else error
  ui1->>-ui: Trả về thông báo lỗi cụ thể khi upload Audio
end

deactivate ui1
ui->>+ui: Cập nhật giao diện
ui-->>-user: Hiển thị kết quả
deactivate ui
deactivate user
```
