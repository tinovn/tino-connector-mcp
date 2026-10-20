# Tino Connector

Manage your Tino account from Claude or ChatGPT: hosting and VPS services, domains, DNS records, invoices and support tickets, within the permissions you approve.

Operated by **TINO GROUP JOINT STOCK COMPANY**. This plugin adds one remote MCP server, `https://api.tino.vn/mcp`. It contains no local code, hooks, scripts or skills.

## Install in Claude Code

```sh
claude plugin marketplace add tinovn/tino-connector-mcp
claude plugin install tino@tinovn
```

In Claude Code, run `/mcp`, select `tino` → **Authenticate**, sign in to your Tino account, review the requested permissions and select **Agree**.

## Connect from Claude or ChatGPT

If your account supports custom MCP connectors, add `https://api.tino.vn/mcp` in the application's connector settings, connect with OAuth and approve the permissions you want to grant. Availability of custom connectors depends on the application and your account.

Read the [connection guide](docs/mcp-connector.md) for permissions, examples and instructions for revoking access. This repository does not indicate approval or availability in either application's directory.

## What it can do

- **Services:** list services and VPS, view details and resources; start, stop or reboot a VPS, change its hostname, renew, order SSL.
- **Domains:** list and inspect domains, change nameservers, register and renew domains, lock or unlock, forwarding.
- **DNS:** read, add, edit and delete DNS zones and records.
- **Billing:** view invoices, balance and transactions; pay invoices from account credit; request a top-up.
- **Support:** read, reply to, close and reopen tickets.

Tools that change data are annotated as write operations. Claude and ChatGPT handle confirmation according to their application settings; review and confirm the intended change before running it. Domain transfer (EPP) codes and registrant changes are never available to the plugin.

Service cancellation is available only in the Tino client dashboard; MCP does not support cancellation.

## Data and access

Each tool call is an HTTPS request to `https://api.tino.vn/mcp` carrying your OAuth token; Tino runs it against your own account and returns the result to the application. The plugin sends nothing anywhere else and has no local storage; the client application manages the OAuth token. Identity fields of account and contact records (ID documents, phone number, postal address, tax and bank data) are removed from responses.

Sign in only through Tino's sign-in page. Do not paste passwords or sign-in codes into a chat. To revoke access, open the authorized applications section of the Tino client area and revoke the relevant application.

## Links

- [Documentation](https://github.com/tinovn/tino-connector-mcp/blob/main/docs/mcp-connector.md)
- [Privacy policy](https://tino.vn/chinh-sach-bao-mat)
- [Terms of service](https://tino.vn/dieu-khoan-su-dung-dich-vu)
- [Support](https://tino.vn/)
- [Apache License 2.0](LICENSE)

## Tiếng Việt

Quản lý tài khoản Tino từ Claude hoặc ChatGPT: dịch vụ hosting/VPS, tên miền, bản ghi DNS, hoá đơn và ticket hỗ trợ, trong phạm vi quyền bạn đồng ý. Đơn vị vận hành: **TINO GROUP JOINT STOCK COMPANY**.

Với Claude Code, chạy hai lệnh cài đặt ở trên, sau đó gõ `/mcp` → `tino` → **Authenticate**, đăng nhập Tino và bấm **Đồng ý**. Với Claude hoặc ChatGPT có hỗ trợ kết nối MCP tuỳ chỉnh, thêm `https://api.tino.vn/mcp` trong phần cấu hình kết nối của ứng dụng rồi cấp quyền qua OAuth.

Yêu cầu hủy dịch vụ chỉ thực hiện trên bảng điều khiển khách hàng Tino; MCP không hỗ trợ thao tác hủy.

Các công cụ thay đổi dữ liệu được đánh dấu là thao tác ghi. Bước hỏi xác nhận do ứng dụng thực hiện theo cấu hình của ứng dụng; hãy kiểm tra và xác nhận nội dung thay đổi trước khi chạy. Không gửi mật khẩu hoặc mã đăng nhập trong cuộc trò chuyện. Để thu hồi quyền, mở phần quản lý ứng dụng đã cấp quyền trong khu vực khách hàng Tino và thu hồi ứng dụng tương ứng.

Xem [tài liệu kết nối](docs/mcp-connector.md), [chính sách bảo mật](https://tino.vn/chinh-sach-bao-mat), [điều khoản sử dụng](https://tino.vn/dieu-khoan-su-dung-dich-vu) và [trang hỗ trợ](https://tino.vn/).
