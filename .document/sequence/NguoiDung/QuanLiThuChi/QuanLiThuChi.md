```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Trang quản lí thu chi
participant manage as Quản lí giao dịch
participant db as Giao dịch
autonumber

user->>+ui: Xem thông tin thu chi, lọc thu chi dựa trên bộ lọc thời gian
activate user
activate ui
ui->>+manage: Xử lí lọc thống kê thu chi dựa trên thời gian đã chọn
activate manage
manage->>+db: Xử lí dữ liệu giao dịch
db->>-manage:Trả về kết quả
manage-->>-ui: Trả về kết quả
ui-->>-user: Hiển thị kết quả

user->>+ui: Để tìm kiếm một giao dịch, mã giao dịch hoặc tên người dùng vào thanh tìm kiếm
ui->>+manage: Xử lí lọc giao dịch dựa trên từ khóa tìm kiếm
manage->>+db: Xử lí dữ liệu giao dịch
manage-->>-ui: Trả về kết quả
ui-->>-user: Hiển thị kết quả
deactivate ui
deactivate user

```
