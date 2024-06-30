```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang chi tiết bài đăng
participant commentTool as Tool lọc bình luận
participant manage as Quản lí bình luận
participant db as Bình luận
autonumber

user->>+ui: Yêu cầu thêm bình luận
activate user
activate ui
ui->>+manage: Xử lí thêm bình luận
activate manage
manage->>+db: Xử lí dữ liệu bình luận
alt Thành công
db->>+commentTool: Xử lí lọc bình luận
commentTool-->>-db: Trả về kết quả lọc
db->>manage:Trả về kết quả thành công
manage-->>-ui:Trả về kết quả
ui->>+ui: Cập nhật thông báo
ui-->>-user: Hiển thị thông báo thành công
else Thất bại
db->>-manage:Trả về thông báo thất bại
manage-->>-ui:Trả về kết quả
ui->>+ui: Cập nhật thông báo
ui-->>-user: Hiển thị thông báo lỗi
end
deactivate ui
deactivate user

```
