# AGENTS.md - Q版人物梗圖庫 (Folder & Image Management System)

本文件旨在規範本專案的「主題資料夾完整生命週期管理（CRUD）」與「梗圖圖片管理」架構。讓 AI 助手在擴充或維護本專案時能保持嚴格的一致性。

---

## 1. 系統功能與架構
- **資料夾管理能力 (Folder CRUD)**：
  1. **Create**：建立主題資料夾，支援上傳自訂封面圖（或自動生成可愛 SVG 預設封面）。
  2. **Read**：首頁卡片式展示所有資料夾封面、主題名稱、簡介與圖片數量計數。
  3. **Update**：支援重新命名資料夾、編輯說明與更換封面圖片。
  4. **Delete**：支援刪除資料夾，並聯級清理（Cascade Delete）該主題底下所有的梗圖。
- **圖片管理能力 (Image Management)**：
  - 進入資料夾後，可上傳圖片至指定 `folderId`。
  - 每張圖片提供即時縮圖預覽、下載檔案與單張刪除功能。

---

## 2. 資料模型 (Data Schema)

### (1) 資料夾資料結構 (Folder Schema)
```json
{
  "id": "folder-001",
  "name": "工作厭世系列",
  "description": "打工人的崩潰日常",
  "coverImage": "封面圖 Data URL (Base64) 或 SVG 字串"
}
