```mermaid
sequenceDiagram
actor user as người dùng
participant ui as Giao diện thanh toán sách mua lẻ
participant manage as Quản lí giao dịch
participant db as Giao dịch
autonumber

user->>+ui: Yêu cầu giao dịch đọc sách
activate user
activate ui
user->>+ui: Nhấn chọn "Mã giảm giá"
ui-->>-user: Trả về giao diện danh sách voucher 
user->>+ui: Chọn voucher phù hợp
ui-->>-user: Trả về giao diện thanh toán với tổng tiền được giảm giá
deactivate ui
deactivate user

```
