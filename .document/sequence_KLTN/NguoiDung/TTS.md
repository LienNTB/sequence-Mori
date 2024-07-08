```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Giao diện đọc sách
participant manage as Quản lí sách
participant db as Quản lí sách
autonumber

user->>+ui: Bấm chọn "Nghe từ đầu trang hiện tại"
activate user
activate ui
ui->>+manage: Xử lí Text to speech
activate manage
manage->>+db: Xử lí dữ liệu audio của sách
db->>manage:Trả về audio của sách từ đầu trang hiện tại
manage-->>-ui:Trả về kết quả
ui->>+ui: Phát audio
ui-->>-user: Phát audio thành công
deactivate ui
deactivate user

```
