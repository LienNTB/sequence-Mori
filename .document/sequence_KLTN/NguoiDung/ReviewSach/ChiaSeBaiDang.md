```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang chi tiết bài đăng
participant facebook as Facebook
participant manage as Quản lí bài đăng
participant db as Bài đăng
autonumber

user->>+ui: Yêu cầu chia sẻ bài đăng
activate user
activate ui
par Xử lí chia sẻ bài đăng tại hệ thống
ui->>+manage: Xử lí chia sẻ bài đăng
manage->>+db: Xử lí dữ liệu bài đăng
activate manage
and Xử lí chia sẻ bài đăng tại Facebook
ui->>facebook: Xử lí chia sẻ bài đăng Facebook
end
deactivate ui
deactivate user

```
