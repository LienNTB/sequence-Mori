```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Giao diện chi tiết sách
participant manage as Quản lí sách
participant db as Sách
autonumber

user->>+ui: Yêu cầu chấm điểm sách theo sao
activate user
activate ui
ui->>+manage: Xử lí chấm điểm sách theo sao
activate manage
manage->>+db: Xử lí dữ liệu đánh giá sách
alt Thành công
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
