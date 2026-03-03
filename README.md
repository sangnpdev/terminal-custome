# Hướng Dẫn Cài Đặt và Tuỳ Biến Terminal

## 1. Cài Đặt Font JetBrainsMono Nerd Font (Regular)

### Bước 1: Cài Đặt Font
- Mở thư mục `JetBrainsMono-Nerd-Font` trong dự án này.
- Nhấp đúp vào file font (thường có đuôi `.ttf` hoặc `.otf`, ví dụ: `JetBrainsMonoNerdFont-Regular.ttf`).
- Nhấn nút **Install** (Cài đặt) để cài font vào hệ thống.

### Bước 2: Áp Dụng Font Cho Terminal
#### Windows Terminal
1. Mở Windows Terminal.
2. Vào **Settings** (Cài đặt) > chọn profile bạn muốn chỉnh (ví dụ: Command Prompt, PowerShell, v.v.).
3. Trong mục **Appearance** (Giao diện), tìm **Font face** và nhập tên font: `JetBrainsMono Nerd Font`
4. Lưu lại cài đặt.

#### VS Code Terminal
1. Mở VS Code, vào **File > Preferences > Settings** (hoặc nhấn `Ctrl + ,`).
2. Tìm kiếm "terminal font family".
3. Thêm dòng sau vào cài đặt:
	```json
	"terminal.integrated.fontFamily": "JetBrainsMono Nerd Font"
	```

## 2. Cài Đặt Oh My Posh Tuỳ Biến Terminal

### Bước 1: Cài Đặt Oh My Posh
- Mở PowerShell với quyền Admin (Run as Administrator).
- Chạy lệnh sau để cài đặt Oh My Posh:
	```powershell
	winget install JanDeDobbeleer.OhMyPosh -s winget
	```

### Bước 2: Thêm Oh My Posh vào PowerShell
- Mở file cấu hình PowerShell (profile):
	```powershell
	notepad $PROFILE
	```

-	Nếu chạy lệnh `notepad $PROFILE` bị lỗi, hãy chạy lần lượt hai lệnh sau:
	```powershell
	if (!(Test-Path $PROFILE)) { New-Item -ItemType File -Path $PROFILE -Force }
	notepad $PROFILE

- Thêm dòng sau vào cuối file:
	```powershell
	oh-my-posh init pwsh --config "$(oh-my-posh get shell-path pwsh)" | Invoke-Expression
	```
- Lưu lại và khởi động lại PowerShell.


### Bước 3: Tuỳ Biến Theme Riêng (Custom Theme)
- Bạn có thể sử dụng file theme JSON tuỳ chỉnh đã cung cấp sẵn: `atomic.omp.json`.
- Đường dẫn file theme: `D:/terminal-custome/atomic.omp.json` (hoặc đúng vị trí bạn lưu file này).

- Để áp dụng theme custom này cho Oh My Posh, thêm dòng sau vào cuối file `$PROFILE`:
	```powershell
	oh-my-posh init pwsh --config "D:/terminal-custome/atomic.omp.json" | Invoke-Expression
	```
- Lưu lại và khởi động lại PowerShell để thấy giao diện mới.

- Nếu muốn chỉnh sửa theme, chỉ cần sửa file `atomic.omp.json` rồi reload lại terminal.

- Tham khảo thêm về cấu trúc file theme tại: https://ohmyposh.dev/docs/themes/

### Lưu ý:
- Nên cài font Nerd Font (như hướng dẫn ở trên) để hiển thị đầy đủ biểu tượng.
- Nếu gặp lỗi font, kiểm tra lại font đã cài và đã chọn đúng trong terminal.

---

## 3. Tránh Lỗi Font Ký Tự Đặc Biệt
- Đảm bảo đã cài đúng font **Nerd Font** (không phải bản thường).
- Sau khi cài đặt, khởi động lại terminal hoặc VS Code để font được áp dụng.
- Nếu vẫn lỗi ký tự, kiểm tra lại tên font đã nhập đúng chưa (`JetBrainsMono Nerd Font`).

-## 4. Tham Khảo
- [Nerd Fonts Documentation](https://www.nerdfonts.com/font-downloads)
- [Cách đổi font cho Windows Terminal](https://learn.microsoft.com/en-us/windows/terminal/customize-settings/profile-font)

---
Nếu có vấn đề về font, hãy kiểm tra lại các bước trên hoặc liên hệ người quản lý dự án để được hỗ trợ.