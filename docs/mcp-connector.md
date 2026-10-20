# Tino Connector — Claude & ChatGPT

## Tiếng Việt

Đơn vị vận hành: **TINO GROUP JOINT STOCK COMPANY**. [Kho mã công khai](https://github.com/tinovn/tino-connector-mcp).

Tino Connector cho trợ lý AI (Claude, ChatGPT) làm việc với tài khoản Tino của bạn: xem và quản lý dịch vụ hosting/VPS, tên miền, bản ghi DNS, hoá đơn và ticket hỗ trợ — bằng câu lệnh thường, trong phạm vi quyền bạn cấp.

**Địa chỉ máy chủ MCP:** `https://api.tino.vn/mcp`

### Kết nối

- **Claude (claude.ai, Claude Desktop, Claude mobile):** Customize → Connectors → tìm "Tino" (khi đã lên danh mục) hoặc *Add custom connector* với URL ở trên → **Connect**.
- **Claude Code:** `claude plugin marketplace add tinovn/tino-connector-mcp` rồi `claude plugin install tino@tinovn`; trong Claude Code gõ `/mcp` → `tino` → *Authenticate*.
- **ChatGPT:** Apps → tìm "Tino" (khi đã lên danh mục), hoặc thêm connector MCP với URL ở trên.

Khi kết nối, trình duyệt mở trang đăng nhập Tino: đăng nhập như thường (mã OTP qua email/SĐT, Google, Zalo hoặc passkey), xem danh sách quyền và bấm **Đồng ý**. Trợ lý không bao giờ thấy mật khẩu hay mã OTP của bạn; nó nhận một mã truy cập có hạn, chỉ dùng được trong các quyền bạn đã đồng ý.

### Quyền và việc trợ lý làm được

| Quyền | Trợ lý làm được |
|---|---|
| Xem thông tin tài khoản | Xem hồ sơ (đã lược giấy tờ, SĐT, địa chỉ), thông báo |
| Xem dịch vụ | Danh sách và chi tiết dịch vụ, VPS, tài nguyên, chứng chỉ SSL |
| Quản lý dịch vụ | Khởi động/tắt/khởi động lại VPS, đổi hostname, gia hạn, đặt chứng chỉ SSL, yêu cầu huỷ dịch vụ |
| Xem tên miền | Danh sách, chi tiết, nameserver, khoá chuyển, gia hạn tự động |
| Quản lý tên miền | Đổi nameserver, đặt mua và gia hạn tên miền, bật/tắt khoá, chuyển tiếp |
| Xem / sửa bản ghi DNS | Đọc, thêm, sửa, xoá bản ghi và vùng DNS |
| Xem hoá đơn | Hoá đơn, số dư, lịch sử giao dịch |
| Thanh toán, nạp tiền | Thanh toán hoá đơn bằng số dư, tạo yêu cầu nạp tiền |
| Ticket | Xem ticket, trả lời, đóng/mở lại |

Mã chuyển tên miền (EPP) và đổi chủ thể tên miền **không bao giờ** cấp cho trợ lý. Mọi thao tác có thay đổi (đặt hàng, thanh toán, huỷ, đổi DNS/nameserver, khởi động lại VPS) được đánh dấu là thao tác ghi. Bước hỏi xác nhận do Claude/ChatGPT thực hiện theo cấu hình của ứng dụng; hãy kiểm tra và xác nhận nội dung thay đổi trước khi chạy.

### Ví dụ

- "Liệt kê VPS của tôi và hạn gia hạn."
- "Tên miền example.vn đang trỏ nameserver nào?"
- "Thêm bản ghi A `www` → 1.2.3.4 cho example.vn."
- "Tôi còn hoá đơn nào chưa thanh toán?"

### Thu hồi quyền

Trong khu vực khách hàng Tino, mở phần quản lý ứng dụng đã cấp quyền và thu hồi quyền của "Claude" hoặc "ChatGPT". Mọi mã truy cập của ứng dụng đó hết hiệu lực ngay.

### Dữ liệu

Trợ lý chỉ đọc/ghi qua API của Tino theo quyền bạn cấp; kết quả được gửi cho Claude/ChatGPT để trả lời bạn. Chính sách bảo mật: [Chính sách bảo mật Tino](https://tino.vn/chinh-sach-bao-mat).

**Điều khoản sử dụng:** [Điều khoản dịch vụ Tino](https://tino.vn/dieu-khoan-su-dung-dich-vu)

**Hỗ trợ:** support@tino.vn · [Trang hỗ trợ Tino](https://tino.vn/)

---

## English

Operated by **TINO GROUP JOINT STOCK COMPANY**. [Public repository](https://github.com/tinovn/tino-connector-mcp).

Tino Connector lets an AI assistant (Claude, ChatGPT) work with your Tino account: view and manage hosting/VPS services, domains, DNS records, invoices and support tickets in plain language, within the permissions you grant.

**MCP server URL:** `https://api.tino.vn/mcp`

### Connect

- **Claude (claude.ai, Claude Desktop, Claude mobile):** Customize → Connectors → find "Tino" (once listed) or *Add custom connector* with the URL above → **Connect**.
- **Claude Code:** `claude plugin marketplace add tinovn/tino-connector-mcp`, then `claude plugin install tino@tinovn`; in Claude Code run `/mcp` → `tino` → *Authenticate*.
- **ChatGPT:** Apps → find "Tino" (once listed), or add an MCP connector with the URL above.

Connecting opens the Tino sign-in page: sign in as usual (one-time code by email/phone, Google, Zalo or passkey), review the permissions and select **Agree**. The assistant never sees your password or one-time code; it receives an expiring access token limited to the permissions you approved.

### Permissions

| Permission | What the assistant can do |
|---|---|
| Account (read) | Profile (without ID documents, phone or address), notifications |
| Services (read) | Service list and details, VPS, resources, SSL certificates |
| Services (manage) | Start/stop/reboot a VPS, change hostname, renew, order SSL, request cancellation |
| Domains (read) | Domain list and details, nameservers, transfer lock, auto-renew |
| Domains (manage) | Change nameservers, register and renew domains, lock/unlock, forwarding |
| DNS (read / edit) | Read, add, edit and delete DNS zones and records |
| Billing (read) | Invoices, balance, transaction history |
| Billing (pay) | Pay invoices from account credit, request a top-up |
| Tickets | Read, reply to, close and reopen tickets |

Domain transfer (EPP) codes and registrant changes are **never** available to an assistant. Every tool that changes something (orders, payments, cancellation, DNS/nameserver changes, VPS restarts) is annotated as a write. Claude and ChatGPT handle confirmation according to the application settings; review and confirm the intended change before running it.

### Examples

- "List my VPS and their renewal dates."
- "Which nameservers does example.vn use?"
- "Add an A record `www` → 1.2.3.4 to example.vn."
- "Do I have unpaid invoices?"

### Revoke access

In the Tino client area, open the authorized applications section and revoke access for "Claude" or "ChatGPT". Every token of that application stops working at once.

### Data

The assistant reads and writes only through Tino's API within the permissions you granted; results go to Claude/ChatGPT to answer you. Privacy policy: [Tino privacy policy](https://tino.vn/chinh-sach-bao-mat).

**Terms:** [Tino terms of service](https://tino.vn/dieu-khoan-su-dung-dich-vu)

**Support:** support@tino.vn · [Tino support](https://tino.vn/)
