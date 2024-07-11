```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Giao diện đọc sách
autonumber

user->>+ui: Bấm chọn nút "Dark mode"
activate user
activate ui
ui-->>-user: Trả về giao diện tối 
user->>+ui: Bấm chọn "Dark mode" một lần nữa
ui-->>-user: Trả về giao diện sáng
deactivate ui
deactivate user

```
