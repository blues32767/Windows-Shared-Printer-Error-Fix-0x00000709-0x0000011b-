# Windows Shared Printer Error Fix (0x00000709 & 0x0000011b)

[![GitHub release](https://img.shields.io/github/v/release/blues32767/Windows-Shared-Printer-Error-Fix-0x00000709-0x0000011b-.svg)](https://github.com/blues32767/Windows-Shared-Printer-Error-Fix-0x00000709-0x0000011b-/releases)
[![GitHub stars](https://img.shields.io/github/stars/blues32767/Windows-Shared-Printer-Error-Fix-0x00000709-0x0000011b-.svg)](https://github.com/blues32767/Windows-Shared-Printer-Error-Fix-0x00000709-0x0000011b-/stargazers)
[![GitHub license](https://img.shields.io/github/license/blues32767/Windows-Shared-Printer-Error-Fix-0x00000709-0x0000011b-.svg)](https://github.com/blues32767/Windows-Shared-Printer-Error-Fix-0x00000709-0x0000011b-/blob/main/LICENSE)

## 中文說明

### 📝 問題描述

在網路辦公環境中，許多 Windows 用戶在連接共用印表機時經常遇到錯誤代碼 0x00000709 和 0x0000011b。這些錯誤可能導致列印工作無法完成，嚴重影響工作流程。本專案提供一個經過實測有效的解決方案，幫助您徹底解決這些惱人的印表機連接問題。

### 🔧 解決方案

根據不同的 Windows 版本，需要更換特定的系統檔案：

#### Windows 10 解決方案
- 更換 `win32spl.dll` 系統檔案

#### Windows 11 解決方案
- 更換 `win32spl.dll`、`localspl.dll` 和 `spoolsv.exe` 系統檔案

### 📥 下載

- [Windows 10 修復包](https://github.com/blues32767/Windows-Shared-Printer-Error-Fix-0x00000709-0x0000011b-/releases/download/v1.20250303/WIN10.-Windows10-Shared-Printer-Error-Fix-0x00000709-0x0000011b.zip)
- [Windows 11 修復包](https://github.com/blues32767/Windows-Shared-Printer-Error-Fix-0x00000709-0x0000011b-/releases/download/v1.20250303/WIN11.-Windows11-Shared-Printer-Error-Fix-0x00000709-0x0000011b.zip)

### 📋 使用說明

1. 下載適合您 Windows 版本的修復包並解壓縮
2. 以系統管理員身份執行 `Fix_PrintSpooler.bat`
3. 這些操作通常需要在「有插 USB 印表機並共用給他人」的那台電腦上進行

### ⚙️ 批次檔案說明

`Fix_PrintSpooler.bat` 批次檔案主要執行以下操作：

1. 停止列印服務（spooler）
2. 對目標系統檔案進行以下處理：
   - 取得檔案所有權
   - 給予管理員和系統完全控制權限
   - 將原檔案重命名為 .old 檔案
   - 複製新檔案到系統目錄
3. 修改註冊表設定：將 RpcAuthnLevelPrivacyEnabled 值設為 0
4. 重新啟動列印服務

### ⚠️ 注意事項

- 對於對更換系統檔案有疑慮的用戶，可以選擇不採取此方法
- 建議在執行批次檔前先備份系統
- 此解決方案主要針對共用印表機錯誤 0x00000709 和 0x0000011b

### 🔄 其他替代解決方案

除了更換系統檔案外，還有其他方法可以嘗試：

1. **設定帳戶認證**：
   - 在分享印表機的電腦上設定帳戶
   - 在共用電腦上新增一個認證帳戶

2. **版本相容性注意事項**：
   - 接印表機的電腦若是 Windows 7、10 或 11 21H2 以下版本，相容性較佳
   - 若接印表機的電腦是 Windows 11 22H2 以上，則只有 Windows 11 或 Windows 10 22H2 能成功安裝驅動
   - Windows 7 在某些條件下可透過改連接埠方式成功連接（例如使用 \\電腦名稱\印表機名稱）
   - Windows 10 可能需要更新至 22H2 版本才能解決問題

---

## English Description

### 📝 Problem Description

In networked office environments, many Windows users frequently encounter error codes 0x00000709 and 0x0000011b when connecting to shared printers. These errors can prevent print jobs from completing, seriously disrupting workflows. This project provides a thoroughly tested and effective solution to help you resolve these frustrating printer connection issues.

### 🔧 Solution

Depending on your Windows version, specific system files need to be replaced:

#### Windows 10 Solution
- Replace the `win32spl.dll` system file

#### Windows 11 Solution
- Replace the `win32spl.dll`, `localspl.dll`, and `spoolsv.exe` system files

### 📥 Downloads

- [Windows 10 Fix Package](https://github.com/blues32767/Windows-Shared-Printer-Error-Fix-0x00000709-0x0000011b-/releases/download/v1.20250303/WIN10.-Windows10-Shared-Printer-Error-Fix-0x00000709-0x0000011b.zip)
- [Windows 11 Fix Package](https://github.com/blues32767/Windows-Shared-Printer-Error-Fix-0x00000709-0x0000011b-/releases/download/v1.20250303/WIN11.-Windows11-Shared-Printer-Error-Fix-0x00000709-0x0000011b.zip)

### 📋 Usage Instructions

1. Download the fix package suitable for your Windows version and extract it
2. Run `Fix_PrintSpooler.bat` as administrator
3. These operations typically need to be performed on the computer that has the USB printer connected and is sharing it with others

### ⚙️ Batch File Explanation

The `Fix_PrintSpooler.bat` batch file performs the following operations:

1. Stops the print spooler service
2. Processes the target system files by:
   - Taking ownership of the files
   - Granting full control permissions to administrators and the system
   - Renaming original files with a .old extension
   - Copying new files to the system directory
3. Modifies registry settings: Sets RpcAuthnLevelPrivacyEnabled value to 0
4. Restarts the print spooler service

### ⚠️ Important Notes

- Users who have concerns about replacing system files may choose not to follow this method
- It's recommended to back up your system before running the batch file
- This solution primarily targets shared printer errors 0x00000709 and 0x0000011b

### 🔄 Alternative Solutions

Besides replacing system files, there are other methods you can try:

1. **Setting Up Account Authentication**:
   - Configure account settings on the computer sharing the printer
   - Add an authentication account on the shared computer

2. **Version Compatibility Considerations**:
   - Computers connecting to printers running Windows 7, 10, or 11 version 21H2 or lower have better compatibility
   - If the computer connecting to the printer is running Windows 11 version 22H2 or higher, only Windows 11 or Windows 10 version 22H2 can successfully install the drivers
   - Windows 7 can successfully connect under certain conditions by modifying the port method (e.g., using \\ComputerName\PrinterName)
   - Windows 10 may need to be updated to version 22H2 to resolve the issue

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/blues32767/Windows-Shared-Printer-Error-Fix-0x00000709-0x0000011b-/issues).

## 📢 Disclaimer

This solution involves replacing system files, which could potentially affect system stability. Use at your own risk. Always back up your system before making such changes.
